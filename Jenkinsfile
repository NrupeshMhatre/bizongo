pipeline {
    agent any
    environment {
        AWS_DEFAULT_REGION = credentials('AWS_DEFAULT_REGION')
        AWS_ACCESS_KEY_ID = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
    stages {
        stage('deploy') {
           steps {
              sh "aws configure set region $AWS_DEFAULT_REGION" 
              sh "aws configure set aws_access_key_id $AWS_ACCESS_KEY_ID"  
              sh "aws configure set aws_secret_access_key $AWS_SECRET_ACCESS_KEY"
              sh "aws s3 cp /bizongo.html s3://bizongo1"
            }
        }
    }
}
