pipeline {
    agent any
    environment {
       AWS_DEFAULT_REGION="us-west-1"
    }
    stages {
        stage('deploy') {
           steps {
              withCredentials([aws(acessKeyVariable:'AWS-ACCESS-KEY_ID',credentialsId:'jenkins',secreteKeyVariable:'AWS_SECRET_KEY')]){
              
              sh "aws s3 cp /bizongo.html s3://bizongo1"
              }
            }
        }
    }
}
