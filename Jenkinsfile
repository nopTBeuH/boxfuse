pipeline {
	agent {
			docker {
				image 'levelup:1'
				args '-v /home/ubuntu/jenkins/tmp:/home/ubuntu/jenkins/tmp'
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
                sh 'rsync -avz target /home/ubuntu/jenkins/tmp'
            }   
        }
    }
}
