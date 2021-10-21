ECR_REGION = 'us-east-1'
ECR_PATH = '826443632289.dkr.ecr.us-east-1.amazonaws.com'
ECR_IMAGE = 'jenkins-test'
VERSION = 'v0.0.1'

app = docker.build("${ECR_PATH}/${ECR_IMAGE}")
echo "app: ${app}"

echo docker.withRegistry("https://${ECR_PATH}", "ecr:us-east-1:AKIA4A27BB2QXSFEVPOE")

node {
    stage('Clone Repository'){
        checkout scm
    }
    stage('Build Image'){

    }
}