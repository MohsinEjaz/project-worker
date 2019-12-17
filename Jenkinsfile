pipeline {
  agent any
  environment {
    registryCredential = 'dockerhub'
  }
  stages {
   stage('build') {
	steps {
	  sh 'docker build -t mohsinejaz/project-fib-worker .'
           }
      }
    stage('Publish') {
        steps{
            script {
                docker.withRegistry( '', registryCredential ) {
		 sh 'docker push mohsinejaz/project-fib-worker:latest'
               } 
           }
        }       
    }
  }
}
