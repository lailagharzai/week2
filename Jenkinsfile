pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh "python sample_unit_test.py"
            }
        }
        stage('Deploy to s3') {
            steps {
                sh "aws configure set region 'eu-west-2'" 
                sh "aws configure set aws_access_key_id 'AKIAR6UCXRSXYY3KTUAL'"  
                sh "aws configure set aws_secret_access_key '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'"
                sh "aws s3 cp www/index.html s3://lailapracticebucket"
                sh "aws s3 cp www/error.html s3://lailapracticebucket"
            }
        }
    }
    post {
        success {
            echo 'success'
        }
        failure {
            echo 'failure'
        }
    }
}
