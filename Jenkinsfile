pipeline {
    agent any
    environment {
       AWS_DEFAULT_REGION="us-west-1"
    }
    stages {
        stage('deploy') {
           steps {
              withCredentials([aws(acessKeyVariable:'AWS-ACCESS-KEY_ID',credentialsId:'jenkins',secreteKeyVariable:'AWS_SECRET_KEY')]){
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(file:'bizongo.html' , bucket:'bizongo1')
              }
            }
        }
    }
}
