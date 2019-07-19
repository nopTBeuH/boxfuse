pipeline {
    agent {
        docker {
            image 'maven:3.3.3'
            args '-v $HOME/.m2:/root/.m2'
        }
    }
    stages {
    	stage ('git') {
            steps {
                git 'https://github.com/nopTBeuH/boxfuse.git'
            }
        }
        stage('Build') {
            docker.image('maven:3.3.3').inside {
                sh 'mvn --version'
            }
        }
    }
}
