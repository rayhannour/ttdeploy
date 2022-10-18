pipeline {
agent any

  
  stages {
  
stage('Checkout Source') {
      steps {
        git url:'https://github.com/rayhannour/ttdeploy.git', branch:'main'
      }
    }

stage('Pull image') {
	 steps{
        	withDockerRegistry([ credentialsId: "dockerhub", url: "" ]) {        		
			sh 'docker pull  090380/smgsapp-v1:v1.01 ' 
			sh 'docker pull  090380/eureka-services-1:latest ' 
			sh 'docker pull  090380/gateway-1:latest ' 
		}
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
