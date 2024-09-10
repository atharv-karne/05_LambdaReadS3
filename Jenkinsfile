pipeline{
    agent any
    stages{
        stage('Terraform Init'){
            steps{
                script{
                    sh 'echo "Running terraform init"'
                    sh 'terraform init'
                    sh 'terraform plan'

                }
            }
        }
        stage('Terraform apply')
        {
            steps{
                withCredentials([aws(credentialsId:"AWS-Cred" , region:"ap-south-1")]){
                script{
                    sh 'terraform apply -auto-approve'
                }
                }
            }
        }
    }
}