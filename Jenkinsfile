pipeline {
    agent any
    stages {
        stage('ínfo'){
            steps{
               echo '¡Hola Mundo!'
               echo $PATH 
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
                environment {
                    PATH = '/usr/local/bin:/usr/bin:/bin:usr/sbin:sbin:/Applications/Docker.app/Contents/Resources/bin/:/Users/alexmarket/Library/Group\ Containers/group.com.docker/Applications/Docker.app/Contents/Resources/bin'
                }
            }
            steps {
                sh "env PATH=$PATH:\$PATH"
                sh 'node --version'
            }
        }
    }
}
