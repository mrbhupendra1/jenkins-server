pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/<your-username>/demo-pipeline.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building project..."
                sh 'echo Hello World > output.txt'
            }
        }

        stage('Test') {
            steps {
                echo "Testing project..."
                sh 'cat output.txt | grep Hello'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying project..."
                sh 'cp output.txt /tmp/deploy.txt'
            }
        }
    }

    post {
        success {
            echo "Pipeline executed successfully ✅"
        }
        failure {
            echo "Pipeline failed ❌"
        }
    }
}
