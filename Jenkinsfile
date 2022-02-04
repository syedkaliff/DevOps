pipeline{
    agent any
     environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
    } 
    tools {
        terraform 'TF'
    }
    stages {
        stage ('Git Checkout'){
            steps{
                git branch: 'main', url:'https://github.com/syedkaliff/DevOps.git'
            }
        }
         
     
        stage (' Terraform Init'){
            steps{
            sh 'terraform init -no-color'
            }
        }
         stage (' Terraform Plan'){
            steps{
            sh 'terraform plan -no-color'
            }
        }
        
         stage (' Terraform Apply -auto-approve'){
            steps{
            sh 'terraform apply -auto-approve -no-color'
            }
        }
       
    }
}
