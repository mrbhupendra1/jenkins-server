pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo "Code is already checked out by Jenkins SCM step ✅"
                sh 'ls -l'
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
            echo "Pipeline failed ❌."
        }
    }
}
