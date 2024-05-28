pipeline{
    agent any
    stages {
        // stage('Checkout from Git'){
        //     steps{
        //         git branch: 'main', url: 'https://github.com/Debiprsansingh/Myntra-jenkins.git'
        //     }
        // }
        stage{
          w
        }
        stage('Terraform version'){
             steps{
                 sh 'terraform --version'
             }
        }
        stage('Terraform init'){
             steps{
                 dir('EKS-TF') {
                      sh 'terraform init'
                   }
             }
        }
        stage('Terraform validate'){
             steps{
                 dir('EKS-TF') {
                      sh 'terraform validate'
                   }
             }
        }
        stage('Terraform plan'){
             steps{
                 dir('EKS-TF') {
                      sh 'terraform plan'
                   }
             }
        }
        stage('Terraform apply/destroy'){
             steps{
                 dir('EKS-TF') {
                      sh 'terraform ${action} --auto-approve'
                   }
             }
        }
    }
}
