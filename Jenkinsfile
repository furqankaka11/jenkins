pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                sh 'docker rmi dockerimage:1.0 -f'
                sh 'docker build -t dockerimage:1.0 . '
            }
        }
    
    
        stage('test') {
            steps {
                sh 'docker stop c1'
                sh 'docker rm c1 -f'
                sh 'docker run -d -p 8081:8081 --name c1 dockerimage:1.0 '
            }
        }
    
    
        stage('deploy') {
            steps {
                echo 'deploying the application..'
            }
        }
    }
}
