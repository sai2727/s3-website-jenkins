pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Deploy to S3') {
            steps {
                script {
                    def awsRegion = 'us-east-1'
                    def bucketName = 'my-awswebsite-bucket'
                    
                    sh "aws s3 sync ./ s3://${bucketName}/ --region ${awsRegion}"
                }
            }
        }
    }
}

