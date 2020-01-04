pipeline {
  agent any
  stages {
    stage('DynamoDB createBucket') {
      steps {
        withAWS(credentials: 'AWS_CREDENTIALS', region: 'us-east-1') {
           sh returnStatus: true, script: "/Library/Frameworks/Python.framework/Versions/3.7/bin/aws dynamodb create-table \
              --table-name terraform-devops321  --attribute-definitions  AttributeName=LockID,AttributeType=S  --key-schema  AttributeName=LockID,KeyType=HASH \
              --provisioned-throughput   ReadCapacityUnits=5,WriteCapacityUnits=5"
       }
    }
   }    
    stage('S3  createBucket') {
      steps {
        withAWS(credentials: 'AWS_CREDENTIALS', region: 'us-east-1') {
           sh returnStatus: true, script: "/Library/Frameworks/Python.framework/Versions/3.7/bin/aws s3 mb s3://terraform-testdevops321 --region=us-east-1"
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
