pipeline {
    agent any
    environment {
        git_credential = "git"
        aws_credential = "jenkins"
        bucket = "bizongo1"
        region = "us-west-1"    
                }
        stage("Upload"){
            steps{
                withAWS(region:"us-west-1", credentials:"jenkins"){
                    s3Upload(file:"bizongo.html", bucket:"bizongo1", path:"/")
                 }
       } 
}
