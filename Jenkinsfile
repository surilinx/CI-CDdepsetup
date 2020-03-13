pipeline {
  agent any
  stages {
	stage ('build') {
	   steps { 
		def mavenHome= "maven", type: "maven"
		sh 'mvn --version'
		sh '''
		  echo "hi this is multiline shell script"
		  ls -lah
		   '''
		}
	}
    }
}
