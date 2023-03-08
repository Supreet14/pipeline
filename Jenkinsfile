pipeline {
    agent any
    stages {
        stage("Terraform init"){
            steps{
                sh("terraform init");
            }
        }
        stage("Terraform Apply"){
            steps{
                echo "terraform action from the parameter is apply"
                input message: 'Do you want to apply ?',ok :'yes'
              sh("terraform apply --auto-approve");
            }
        }
      stage("Terraform Destroy"){
        steps{
              echo "terraform action from the parameter is destroy"
                input message: 'Do you want to destroy ?',ok :'yes'
                sh("terraform destroy --auto-approve");
            }
        }
    }
}
