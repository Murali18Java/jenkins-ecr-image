pipeline {
  environment {
    registry = '540451631109.dkr.ecr.us-east-1.amazonaws.com/jenkins-ecr-cicd'
    registryCredential = 'aws-ecr-credentials'
    dockerImage = ''
  }
  agent any
  stages {
//   stage('Create ECR repository') {
//       steps {
//             withAWS(credentials: 'aws-ecr-credentials', region: 'us-east-1') {
//                   sh "chmod +x ./create_repo.sh"
//                   sh "./create_repo.sh"
//                 }
//             }
//       }
    
  stage('Destroy ECS container') {
      steps {
            withAWS(credentials: 'aws-ecr-credentials', region: 'us-east-1') {
                  sh "chmod +x ./ec2_down.sh"
                  sh "./ec2_down.sh"
                }
            }
      }
    
   
    
    
//     stage('Building image') {
//       steps{
//         script {
//           dockerImage = docker.build registry + ":latest"
//           sh 'echo $dockerImage'
//         }
//       }
//     }
//     stage('Push Image to AWS ECR') {
//         steps{
//             script{
//                 docker.withRegistry("https://" + registry, "ecr:us-east-1:" + registryCredential) {
//                     dockerImage.push()
//                 }
//             }
//         }
//     }
    
//     stage('Deploy docker image to AWS ECS container') {
//             steps {
//                 withAWS(credentials: 'aws-ecr-credentials', region: 'us-east-1') {
//                   sh "chmod +x ./jenkins_ecr.sh"
//                   sh "./jenkins_ecr.sh"
//                 }
//             }
//         }
    }
}
