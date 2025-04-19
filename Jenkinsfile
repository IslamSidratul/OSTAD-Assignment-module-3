pipeline {
    agent any

    environment {
        NODE_ENV = 'development'
    }

    stages {

        stage('Clone') {
            steps {
                echo 'Cloning repository.'
                git url: 'https://github.com/IslamSidratul/OSTAD-Assignment-module-3.git', branch: 'main'
            }
        }

        stage('Install') {
            steps {
                echo 'Installing dependencies...'
                bat 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // This shows test output in Jenkins console
                bat 'npm run check'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed due to an error in one of the stages.'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
    }
}
