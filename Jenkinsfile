pipeline {
  agent any
  environment {
    PATH = "{PATH}:${getTerraformPath()}"
  }
  stages {
    stage('terraform init') {
      steps {
        /bin/sh 'echo "Hello"'
      }
    }

  }
}

def getTerraformPath(){
  def tfHome = tool name: 'Terraform', type: 'org.jenkinsci.plugins.terraform.TerraformInstallation'
  return tfHome
}