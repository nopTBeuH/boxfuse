pipeline {
	agent {
			docker {
				image 'maven:3.6.1-jdk-11-slim' 
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
                sh 'mvn *.war'
            }
        }
        stage ('deploy') {
            steps {
                rsync ''
            }   
        }
    }
}
