pipeline {
  agent any
  environment {
    PATH = "{PATH}:${getTerraformPath()}"
  }
  stages {
    stage('terraform init') {
      steps {
        sh 'terraform init"'
      }
    }

  }
}

def getTeerraformPath(){
   def tfHome = tool name: 'Terraform', type: 'org.jenkinsci.plugins.terraform.TerraformInstallation'
   return tfHome
}