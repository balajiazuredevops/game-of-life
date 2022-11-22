pipeline {
    agent { label 'GOL'}
    stages {
        stage('scm') {
            steps {

                git 'https://github.com/balajiazuredevops/game-of-life.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn package'
            }
        }
    }
    post {
        success {
            archive '**/gameoflife.war'
            junit '**/TEST-*.xml'
        }
        
    }
}