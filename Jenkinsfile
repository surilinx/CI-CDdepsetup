pipeline {
  agent any
  stages {
	stage ('build') {
	   steps {
		sh 'mvn --version'
		sh '''
		  echo "hi this is multiline shell script"
		  ls -lah
		   '''
		}
	}
    }
}
