pipeline {
    agent { label 'GOL'}
    stages {
        stage('scm') {
            steps {

                git branch:'master', url:'https://github.com/balajiazuredevops/game-of-life.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean package'
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