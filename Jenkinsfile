pipeline {
    agent any 
    stages {
        stage('Build') {
          steps {
            ansible --version    
            python --version   
            which zip   
            echo "Build and test the code here..."
          }
        }    

        stage('Test') {
          steps {                    
            echo "Test the code here..."
          }
        }            

        stage('Package') {
          steps {                    
            echo "Package the code here..."
          }
        }     

        stage('Publish') {
          steps {                    
            echo "Publish the code here to ECR/S3 etc., ..."
            sh "git --version"
            sh "ansible --version"
            sh "terraform --version"
          }
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