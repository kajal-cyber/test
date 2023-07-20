pipeline {
    environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_credentials')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_credentials')
    }
    agent any
  stages {

    stage('checkout') {
            steps {
                 script{
                        dir("terraform")
                        {
                            git branch: 'main', url: 'https://github.com/kajal-cyber/test.git'
                        }
                    }
                }
            }
        stage('Terraform init') {
            steps {
                 sh 'pwd;cd terraform/ ; terraform init'
            }
        }
       stage('Terraform plan') {
            steps {
                sh 'pwd;cd terraform/ ; terraform plan'
            }
        }
     
        stage('Terraform apply') {
            steps {
                sh 'pwd;cd terraform/ ; terraform apply --auto-approve'
            }
        }
      stage('Terraform destory') {
            steps {
                sh 'pwd;cd terraform/ ; terraform destroy --auto-approve'
            }
        }
        
    }
}
        
