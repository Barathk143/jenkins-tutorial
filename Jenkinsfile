ECR_REGION = 'us-east-1'
ECR_PATH = '826443632289.dkr.ecr.us-east-1.amazonaws.com'
ECR_IMAGE = 'jenkins-test'

app = docker.build("${ECR_PATH}/${ECR_IMAGE}")
echo "app: ${app}"

node {
    stage('Clone Repository'){
        checkout scm
    }

    stage('Build to ECR'){
        // Docker Build and Push to ECR
        docker.withRegistry("https://${ECR_PATH}", 'ecr:us-east-1:jenkins-aws-anderson-credentials'){
            def image = docker.build("${ECR_PATH}/${ECR_IMAGE}:${env.BUILD_ID}")
            image.push()
        }
    }
    stage('Kubernetes'){
        sh "/home/ubuntu/bin/kubectl get pods"

    }
}
