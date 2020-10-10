pipeline {
    agent any

    stages {
        stage('Pulling Code From SCM') {
            steps {
                echo 'Pushing....'
            }
        }
        stage('Deploy') {
            steps {
                sh 'aws s3 cp . s3://learningtojenkins --recursive --acl public-read'
                sh 'aws s3 website s3://learningtojenkins/ --index-document index.html --error-document error.html'
            }
        }
    }
}
