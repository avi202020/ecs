pipeline {
  agent any
  stages {
    stage('S3  createBucket') {
      steps {
        withAWS(credentials: 'AWS_CREDENTIALS', region: 'us-east-1') {
           sh returnStatus: true, script: /Library/Frameworks/Python.framework/Versions/3.7/bin/aws s3 mb s3://terraform-testdevops321 --region=us-east-1'
       }
    }
   }
   stage('terraform init') {
      steps {
        sh '/usr/local/bin/terraform init'
        withAWS(credentials: 'AWS_CREDENTIALS', region: 'us-east-1') {
           sh '/Library/Frameworks/Python.framework/Versions/3.7/bin/aws iam get-user'
       }
      }
    }
  }
}
