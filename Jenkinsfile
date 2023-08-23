pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = 'us-east-1'
    }

    stages {
        stage('Checkout Repository') {
            steps {
                // Clone the Git repository
                git branch: 'feature', url: 'https://github.com/sai2727/s3-website-jenkins.git'
            }
        }
        stage('Deploy to S3') {
            steps {
                // Use AWS CLI to sync repository contents to S3 bucket
                  
                    def bucketName = 'my-awswebsite-bucket'
                    
                    sh "aws s3 sync ./ s3://${bucketName}"
            }
        }
    }
}
