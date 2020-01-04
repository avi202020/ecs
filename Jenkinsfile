pipeline {
  agent any
  stages {
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