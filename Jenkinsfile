pipeline {
    agent any
    stages {
        stage('deploy') {
            steps {
                  withAWS(region:'us-west-1',credentials:'jenkins') {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'bizongo.html', bucket:'bizongo1')
                  }
        }
    }
}
