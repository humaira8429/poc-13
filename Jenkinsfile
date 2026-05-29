pipeline {
    agent any

    stages {

        stage('Initialize') {
            steps {
                echo "Starting CI/CD Pipeline..."
            }
        }

        stage('Build') {
            steps {
                echo "Building application..."
                sleep 2
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                sleep 2
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying application to environment..."
                sleep 2
            }
        }

        stage('Verification') {
            steps {
                echo "Application deployed successfully!"
            }
        }
    }
}
