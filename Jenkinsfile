pipeline {
  agent any
  stages {
	stage ('build') {
	   steps { 
		sh '''
		  echo "hi this is multiline shell script"
		  ls -la /var/lib/jenkins
		   '''
		}
	}
    }
}
