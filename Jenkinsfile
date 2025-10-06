pipeline {
    agent none
    stages {
        stage('Diag Docker') {
             agent {
                docker { image 'php:8.2-cli' }
            }
          steps {
                sh '''
                 set -x
               whoami
            '''
  }
}


        
        stage('Diag') {
            agent {
                docker { image 'php:8.2-cli' }
            }
            steps {
                sh '''
                  set -x
                  whoami
                  id
                  ls -l /var/run/docker.sock || true
                  docker version || true
                '''
              }
        }
        stage('Checkout') {
            agent {
                docker { image 'php:8.2-cli' }
            }
            steps {
                sh 'php --version'
            }
        }
        stage('Compilation') {
            agent {
                docker { image 'php:8.2-cli' }
            }
            steps {
                sh 'echo "Compilando..."'
            }
        }
        stage('Build') {
            agent {
                docker { image 'php:8.2-cli' }
            }
            steps {
                sh 'echo "docker build -t my-php-app ."'
            }
        }
        stage('Deploy') {
            agent {
                docker { image 'php:8.2-cli' }
            }
            steps {
                sh 'echo "docker run my-php-app ."'
            }
        }
    }
}
