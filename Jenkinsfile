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
                echo 'Uploading files to S3'
                sh 'aws s3 cp www/ s3://lailapracticebucket --recursive'
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
