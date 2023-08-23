pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = 'us-east-1'
    }

    stages {
        stage('Checkout Repository') {
            steps {
                // Clone the Git repository
                git branch: 'feature', url: ''
            }
        }
        stage('Deploy to S3') {
            steps {
                // Use AWS CLI to sync repository contents to S3 bucket
                sh "aws s3 sync ./ my-awswebsite-bucket"
            }
        }
    }
}
