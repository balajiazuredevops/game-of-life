pipeline {
    agent { label 'GOL'}
   

    stages {
      stage('SCM'){
         steps{
           git 'https://github.com/balajiazuredevops/game-of-life.git'
      }
      }
        stage('Build') {
          steps{
            sh "mvn  clean package"
          }  
           }

            post {
                // If Maven was able to run the tests, even if some of the test
                // failed, record the test results and archive the jar file.
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
    }

