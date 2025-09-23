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
                bat 'docker tag registration:v1 meghanapuram6/registration:v1'
                bat 'docker push meghanapuram6/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f D:/DevOps/Week-2/deployment.yaml'
                bat 'kubectl apply -f D:/DevOps/Week-2/service.yaml'
            }
        }
        stage('Automated UI Test') {
            steps {
                bat 'python D:/DevOps/Week-2/test_registration.py'
            }
        }
    }
}
