pipeline {
	agent {
			docker {
				image 'maven:3-alpine' 
				args '-v /root/.m2:/root/.m2'  
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
                sh 'mvn package'
            }
        }
        stage ('deploy') {
            steps {
                rsync ''
            }   
        }
    }
}
