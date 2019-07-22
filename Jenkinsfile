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
                sh 'rsync -avz ./target ubuntu@18.195.195.164:/var/lib/tomcat8/webapps'   
            } 
	}
	stage ('restart web server service') {
	    steps {
                sh 'ssh ubuntu@18.195.195.164 sudo systemctl restart tomcat8.service'   
            } 
	}
    }
}
