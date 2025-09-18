apurapipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t registration:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                bat 'docker tag registration:v1 meghanapuram/registration:v1'
                bat 'docker push meghanapuram6/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f C:\Users\Admin\Documents\1290\Week9/deployment.yaml'
                bat 'kubectl apply -f C:\Users\Admin\Documents\1290\Week9/service.yaml'
            }
        }
        stage('Automated UI Test') {
            steps {
                bat 'python C:\Users\Admin\Documents\1290\Week9test_registration.py'
            }
        }
    }
}
