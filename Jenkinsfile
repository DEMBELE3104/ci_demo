pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps { checkout scm }
        }
        stage('Set up Python') {
            steps {
                bat 'python -m venv venv'
                bat '.\\venv\\Scripts\\activate && pip install --upgrade pip'
            }
        }
        stage('Run tests') {
            steps {
                bat '.\\venv\\Scripts\\activate && python -m unittest discover -s tests'
            }
        }
    }
    post {
        success { echo 'Pipeline completed successfully!' }
        failure { echo 'Pipeline failed.' }
    }
}
