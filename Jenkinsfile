pipeline {
agent any

  
  stages {
  
stage('Checkout Source') {
      steps {
        git url:'https://github.com/rayhannour/ttdeploy.git', branch:'main'
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
