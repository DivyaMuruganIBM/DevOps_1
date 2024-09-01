pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/DivyaMuruganIBM/DevOps_1.git'
            }
        }
        stage('Build') {
            steps {
                sh 'echo "Building the project..."'
                sh 'echo "Your HTML project doesn\'t require any build step!"'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Deploying the project..."'
                sh 'scp -r * https://my-html-project-bucket.s3.us-south.cloud-object-storage.appdomain.cloud/index.html'
            }
        }
    }
}
