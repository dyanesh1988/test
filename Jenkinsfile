pipeline {
    agent any

    stages {
        stage('Pulling Code From SCM') {
            steps {
                echo 'Pulling....'
            }
        }
        stage('Deploy') {
            steps {
                input message: 'Do you want to Deploy website? (Click "Proceed" to continue)'
                sh 'aws s3 cp . s3://buket1988 --recursive --acl public-read'
            }
        }
        stage('Setting Permission') {
            steps {
                sh 'aws s3 website s3://buket1988/ --index-document index.html --error-document error.html'
            }
        }
    }
}
