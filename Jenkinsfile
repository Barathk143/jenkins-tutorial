AWS_REGION = 'us-east-1'
ECR_URI = '826443632289.dkr.ecr.us-east-1.amazonaws.com/jenkins-test'
VERSION = 'v0.0.1'

node {
    stage('Clone Repository'){
        checkout scm
    }
    stage('Build Image'){
        echo "haha: ${ECR_URI}"
    }
}