pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git branch: "main",
          credentialsId: 'git',
          url: 'https://github.com/NrupeshMhatre/bizongo.git'
      }
    }

    stage('deploy') {
           steps {
             withAWS(region:'us-east-1',credentials:'jenkins'){
               
              sh "aws configure set region $AWS_DEFAULT_REGION" 
              sh "aws configure set aws_access_key_id $AWS_ACCESS_KEY_ID"  
              sh "aws configure set aws_secret_access_key $AWS_SECRET_ACCESS_KEY"
              sh "aws s3 cp /bizongo.html s3://bizongo1"
            }
            }
        }
    }
