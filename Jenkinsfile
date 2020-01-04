pipeline {
  agent any
  environment {
    PATH = "{PATH}:${getTerraformPath()}"
  }
  stages {
    stage('terraform init') {
      steps {
       /usr/local/bin/terraform -version
      }
    }

  }
}

def getTerraformPath(){
  def tfHome = tool name: 'Terraform', type: 'org.jenkinsci.plugins.terraform.TerraformInstallation'
  return tfHome
}