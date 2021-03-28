pipeline {
    agent any 
    stages {
        stage('Build') {
            echo "Build and test the code here..."
        }    

        stage('Test') {
            echo "Test the code here..."
        }            

        stage('Package') {
            echo "Package the code here..."
        }     

        stage('Publish') {
            echo "Publish the code here to ECR/S3 etc., ..."
        }   

        stage('Deploy') {
            steps {
                withAWS(credentials: 'radiant-dash-aws-credentials', region: 'us-east-1') {
                    sh "aws s3 ls"
                }
            }
        }
    }
}