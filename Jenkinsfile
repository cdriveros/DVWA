pipeline {
    agent none
    stages {
        stage('Diag Docker') {
             agent {
                docker { image 'php:8.2-cli - holaaaaaaaaaaaaa' }
            }
          steps {
                sh '''
                set -x
              whoami
              id
              ls -ld /Users/carlos.riveros /Users/carlos.riveros/.docker /Users/carlos.riveros/.docker/run
              ls -l  /Users/carlos.riveros/.docker/run/docker.sock
              printenv | grep -E 'DOCKER_HOST|HOME'
              docker version
              docker run --rm hello-world
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
