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

                echo "terraform action from the parameter is apply"
                input message : 'Do you want to destroy ?',ok :'yes' 

                sh("terraform destroy --auto-approve");

            }

        }

    }

}
