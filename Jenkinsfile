pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/humaira8429/poc-13.git'
            }
        }

        stage('Terraform Init') {
            steps {
                sh 'terraform init'
            }
        }

        stage('Terraform Apply') {
            steps {
                sh 'terraform apply -auto-approve'
            }
        }

        stage('Update kubeconfig') {
            steps {
                sh 'aws eks update-kubeconfig --region ap-south-1 --name poc-eks-cluster'
            }
        }

        stage('Deploy to EKS') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }

        stage('Get Service URL') {
            steps {
                sh 'kubectl get svc'
            }
        }
    }
}
