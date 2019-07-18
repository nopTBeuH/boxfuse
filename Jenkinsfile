pipeline {
	agent {
		docker {
			image 'maven:3-alpine' 
			args '-v /tmp:/tmp' 
		}
	}
	stages {
		stage ('git') {
			steps {
				git 'https://github.com/nopTBeuH/boxfuse.git'
			}
		}
		stage ('build') {
			steps {
				sh 'mvn -B'
			}
		}
		stage ('deploy') {
			steps {
				rsync ''
			}   
		}
	}
}
