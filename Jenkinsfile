pipeline {
    agent { docker { image 'node:18.16.0-alpine'
                     args '-e PATH=/usr/local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin'
                   } 
          }
    stages {
        stage('build'){
            steps{ 
                sh 'echo $PATH'
                sh 'node --version'
            } 
        }
    }    
}
