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
                // Replace with the appropriate deployment command for your environment
                sh 'ibmcloud login --apikey bWF0FEf9Yr3Pf8-PtVod7zEYtjz-ufQmQAlVXrD7BpMe'
                sh 'ibmcloud cos object-put --bucket my-html-project-bucket --key index.html --file path/to/local/index.html'
            }
        }
    }
}
