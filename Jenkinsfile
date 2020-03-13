peline {
  agent any
##{ docker {image 'maven:3.3.3' } }
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
