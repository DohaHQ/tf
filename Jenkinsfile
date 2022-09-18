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
                dir('cloudfront-build') 
                {
                sh 'terraform init'
                }
            }
        }

        stage('terraform Plan') {
            steps{
                dir('cloudfront-build') 
                {
                sh 'terraform plan'
                }
            }
        }

        stage('terraform apply') {
            steps{
                dir('cloudfront-build') 
                {
                sh 'terraform apply --auto-approve'
                }
            }
        }
    }

    
}
