pipeline {
	agent {
			docker {
				image 'levelup:1'
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
                sh 'rsync -avz . /home/ubuntu/jenkins/tmp'
            }   
        }
    }
}
