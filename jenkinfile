pipeline {

    agent any

 

    stages {

        

        stage("Terraform init"){

            steps{

                sh("terraform init");

            }

        }

        stage("Terraform Action"){

            steps{

                

                sh("terraform apply --auto-approve");

            }

        }

    }

}
