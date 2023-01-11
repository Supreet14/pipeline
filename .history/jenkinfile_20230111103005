pipeline {

    agent any

 

    stages {

        stage('checkout') {

            steps {

             checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: '87ef74fb-7d42-42dd-8582-f6991b6fd2c5', url: 'https://github.com/Deerasa921/ec2mah']])

            }

        }

        stage("Terraform init"){

            steps{

                sh("terraform init");

            }

        }

        stage("Terraform Action"){

            steps{

                echo "terraform action from the parameter is --> ${action}"

                sh("terraform ${action} --auto-approve");

            }

        }

    }

}