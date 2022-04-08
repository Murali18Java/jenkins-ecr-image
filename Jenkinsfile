pipeline {
  environment {
    registry = '502629635618.dkr.ecr.ap-south-1.amazonaws.com/jenkins-cicd'
    registryCredential = 'jenkins-ecr'
    dockerImage = 'aws-ecr'
  }
  agent any
  stages {
    stage('Build docker image') {
      steps{
        script {
          dockerImage = docker.build registry + "myapp:$BUILD_NUMBER"
        }
      }
    }
    stage('Push image to ECR') {
        steps{
            script{
                docker.withRegistry("https://" + registry, "ecr:ap-south-1:" + registryCredential) {
                    dockerImage.push()
                }
            }
        }
    }
  }
}