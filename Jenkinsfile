pipeline {
    agent any
    stages {
        stage('test AWS credentials') {
            steps {
                withAWS(credentials: 'aws-ecr', region: 'ap-south-1') {
                    sh 'jenkins_ecr.sh'
                }
            }
        }
    }
}