@Library("shared-library") _
pipeline {

    agent any

 parameters {
        choice(
            name: 'Action',
            choices: ['Build', 'Destroy'],
            description: 'The action to take'
        )
 }
    stages {
        stage("Initialisation"){
            steps{
                sh("terraform init");
            }
        }
        stage('Approval') {
            steps {
                action();
            }
        }
        stage('Apply') {
            steps {
               terraformPlan();
            }
        }
    }
}
def terraformPlan() {
    // Setting Terraform Destroy flag
    if(params.Action == 'Build') {
         sh("terraform apply --auto-approve");
    } else if (params.Action == 'Destroy'){
        sh("terraform destroy --auto-approve");
    }
}

  

 

