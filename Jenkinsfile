pipeline{

  tools{
    maven 'mymaven'
  }

  environment {
    application = "springbootapp"
   }

	agent any

	stages {

	   stage('Clone repository') {
		     steps{
				      git 'https://github.com/adititdkr1311/ELK-Logging-Monitoring'
			     }
	   }

   	stage('Build image') {
		   steps{
		        sh 'docker build -t myimagespring:${BUILD_NUMBER} .'
				}
	  }

	  stage('Deploy application') {
			 steps{
	        	sh ("docker run -d -p 81:8080 -v /var/log/:/var/log/ myimagespring:${BUILD_NUMBER}")
	      }
    }

	}

}
