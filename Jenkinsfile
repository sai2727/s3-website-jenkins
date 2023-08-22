pipeline {
    agent any

    stages{
        stage('deploy to S3'){
            steps{
                sh 'aws s3 cp public/index.html s3://my-awswebsite-bucket'
                sh 'aws s3api put-object-acl --bucket my-awswebsite-bucket --key index.html --acl public-read'
                sh 'aws s3 cp public/error.html s3://my-awswebsite-bucket'
                 }
        }
    }
    post{
        always{
            cleanWs disableDeferredWipeout: true, deleteDirs: true
        }
    }

}
