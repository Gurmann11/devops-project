pipeline {
    agent any

    environment {
        IMAGE_NAME = "flask-app"
        CONTAINER_NAME = "flask-container"
    }

  stages {

    stage('Clone Code') {
        steps {
            git branch: 'main', url: 'https://github.com/Gurmann11/devops-project.git'
        }
    }

    stage('Build Docker Image') {
        steps {
            sh 'docker build -t $IMAGE_NAME .'
        }
    }

    stage('Scan Docker Image') {
        steps {
            sh 'trivy image $IMAGE_NAME'
        }
    }

    stage('Stop Old Container') {
        steps {
            sh '''
            docker stop $CONTAINER_NAME || true
            docker rm $CONTAINER_NAME || true
            '''
        }
    }

    stage('Run New Container') {
        steps {
            sh '''
            docker run -d -p 5000:5000 --name $CONTAINER_NAME $IMAGE_NAME
            '''
        }
    }
}
