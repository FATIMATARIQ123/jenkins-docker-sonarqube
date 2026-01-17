pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Yeh step GitHub se aapka code fetch karega
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Aapki image ka naam 'my-nginx-app' rakha hai
                    sh 'docker build -t my-nginx-app .'
                }
            }
        }

        stage('Test') {
            steps {
                echo 'Testing if image exists...'
                sh 'docker images | grep my-nginx-app'
            }
        }
    }
}
