node('GOL') {
    stage('SCM'){
     git 'https://github.com/balajiazuredevops/game-of-life.git'
    }
    stage('build'){
    build 'mvn clean package'
    }
    stage('postbuild'){
       junit '**/TEST-*.xml'
    }
    stage('archiveartifacts'){
        archive '**/*.war\''
    }

    }
  
