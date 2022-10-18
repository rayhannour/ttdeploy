pipeline {
agent any

  
  stages {
  
stage('Checkout Source') {
      steps {
        git url:'https://github.com/rayhannour/ttpipeline.git', branch:'main'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "deployment.yaml", kubeconfigId: "kubernetes")
        }
      }
    }
  	
	



   }
}
