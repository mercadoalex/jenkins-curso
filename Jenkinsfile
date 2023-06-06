pipeline {
    agent any
    stages {
        stage('ínfo'){
            steps{
               echo '¡Hola Mundo!'
            }
        }
        stage('Build Node') {
            agent {
                docker {
                    image 'node:18.16.0-alpine'
                    label 'docker-agent'
                    args  '-v /tmp:/tmp'
                    
                    // Run the container on the node specified at the
                    // top-level of the Pipeline, in the same workspace,
                    // rather than on a new node entirely:
                    reuseNode true
                }
            }
            steps {
                sh "env PATH=$PATH:\$PATH"
                sh 'node --version'
            }
        }
    }
}
