pipeline{
    agent any
    stages{
        stage('Terraform Init'){
            steps{
                script{
                    sh 'echo "Running terraform init"'
                    sh 'terraform init'

                }
            }
        }
        stage('Terraform apply')
        {
            steps{
                withCredentials([aws(credentialsId:"AWS-Cred" , region:"ap-south-1")]){
                script{
                    sh 'terraform plan'
                    sh 'terraform apply -auto-approve'
                }
                }
            }
        }
        stage('Terraform destroy')
        {
            steps{
                withCredentials([aws(credentialsId:"AWS-Cred" , region:"ap-south-1")]){
                script{
                    sh 'terraform destroy'
                }
                }
            }
        }
    }
}