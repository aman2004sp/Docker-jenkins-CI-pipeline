pipeline {
    agent any

    environment {
        IMAGE_NAME = "flask-app"
        CONTAINER_NAME = "flask-container"
        PORT = "5000"
    }

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/aman2004sp/docker-jenkins-ci-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Stop Existing Container') {
            steps {
                sh '''
                docker stop $CONTAINER_NAME || true
                docker rm $CONTAINER_NAME || true
                '''
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p $PORT:$PORT --name $CONTAINER_NAME $IMAGE_NAME'
            }
        }
    }

    post {
        success {
            echo 'Deployment successful'
        }
        failure {
            echo 'Deployment failed'
        }
    }
}
