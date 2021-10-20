pipeline {
    agent any
    environment {
        AWS_REGION = 'us-east-1'
        ECR_URI = '826443632289.dkr.ecr.us-east-1.amazonaws.com/jenkins-test'
        VERSION = 'v0.0.1'

        docker_image = ''
    }
    stages {
        stage('Building Docker Image') {
            steps {
                docker_image = docker.build("https://${ECR_URI}", 'ecr.us-east-1.amazonaws.com/jenkins-test')
                echo "docker_image: ${docker_image}"
            }
        }
        stage('Deploy Image') {
            steps {
                echo 'Deploy Image ${AWS_REGION}'
            }
        }
        stage('Build') {
            steps {
                echo 'Building.. ${VERSION}'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
