pipeline {
    agent any
        environment {
		DOCKERHUB_CREDENTIALS=credentials('DockerHub')
	}
    stages {
        stage('Cloning our Git') {
            steps {
                git 'https://github.com/OdayMahamid/devOps-project.git'
            }
        }
        stage('Building our image') {
            steps{
                sh 'sudo docker build -t web .'
            }
        }
        stage('Login') {
	    steps {
		sh 'echo $DOCKERHUB_CREDENTIALS_PSW | sudo docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
	    }
	}  
	stage('Tag') {
	    steps {
	         sh 'sudo docker tag web oday2211/web'
	     }
	}
        stage('Push') {
            steps {
		sh 'sudo docker push oday2211/web'
	   }  
        }
    }
}
