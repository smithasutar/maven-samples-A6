pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build & Test') {
            steps {
                sh 'mvn clean test'
            }
        }
    }

    post {
        success {
            echo 'Build SUCCESS: All tests passed'
        }
        failure {
            echo 'Build FAILURE: Tests failed (bug detected)'
        }
    }
}
