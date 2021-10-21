EKR_API = 'https://2ABF4B00A5858CE072BD19CE13ADCCA3.gr7.us-east-1.eks.amazonaws.com'
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
        withKubeConfig([credentialsId: "jenkins-aws-anderson-credentials",
                        serverUrl: "${EKR_API}"]){
            sh "kubectl get pods"
        }


    }
}
