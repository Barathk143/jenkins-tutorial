pipeline {
    agent any
    environment {
        AWS_REGION = 'us-east-1'
        AWS_ECR_URL = 'http://826443632289.dkr.ecr.us-east-1.amazonaws.com/jenkins-test'
        VERSION = 'v0.0.1'

        docker_image = ''
    }
    stages {
        stage('Building Docker Image') {
            steps {
                echo 
            }
        }
        stage('Deploy Image') {
            steps {
                echo 'Deploy Image'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
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
