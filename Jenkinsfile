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
                sh '''
                echo "Deploying the project..."
                ibmcloud login --apikey bWF0FEf9Yr3Pf8-PtVod7zEYtjz-ufQmQAlVXrD7BpMe -r us-south
                ibmcloud cos upload --bucket my-html-project-bucket --key index.html --file index.html
                ibmcloud cos upload --bucket my-html-project-bucket --key other-file.html --file other-file.html
                '''
            }
        }
    }
}
