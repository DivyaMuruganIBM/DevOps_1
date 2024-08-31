pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'git url: 'https://github.com/DivyaMuruganIBM/DevOps_1.git',', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                sh 'npm install' // Replace with your build command
            }
        }
        stage('Test') {
            steps {
                sh 'npm test' // Replace with your test command
            }
        }
        stage('Package') {
            steps {
                sh 'npm run build' // Replace with your package command
            }
        }
        stage('Deploy to IBM Cloud') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'ibm-cloud-api-key', variable: 'IBM_CLOUD_API_KEY')]) {
                        sh """
                           ibmcloud login --apikey $IBM_CLOUD_API_KEY -r us-south
                           ibmcloud cf push your-app-name -p ./build-folder
                        """
                    }
                }
            }
        }
    }
}
