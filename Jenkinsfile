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

    stage('Upload to S3') {
        steps{
            script {

                dir(''){

                    pwd(); //Log current directory

                    withAWS(region:'us-west-1',credentials:'jenkins') {

                        def identity=awsIdentity();//Log AWS credentials

                        // Upload files from working directory '' in your project workspace
                        s3Upload(bucket:"bizongo1", workingDir:'', includePathPattern:'**/*');
                    }

                };
            }
        }
    }

  }

}
