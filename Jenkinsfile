pipeline {
    agent any
    tools {
       terraform 'terraform'
    }
    stages {
        stage('Git checkout') {
           steps{
                git branch: 'main', credentialsId: 'Github', url: 'https://github.com/DohaHQ/tf.git'
            }
        }
        
        stage('terraform Init') {
            steps{
                sh 'terraform init'
            }
        }

        stage('terraform Plan') {
            steps{
                sh 'terraform plan'
            }
        }

        stage('terraform apply') {
            steps{
                sh 'terraform apply --auto-approve'
            }
        }
    }

    
}