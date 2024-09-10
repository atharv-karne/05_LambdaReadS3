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
        },
        stage('Terraform apply')
        {
            steps{
                script{
                    sh 'terraform apply -auto-approve'
                }
            }
        }
    }
}