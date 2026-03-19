pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Pull latest code from repo
                checkout scm
            }
        }

        stage('Build & Test') {
            steps {
                // Run Maven tests (same as what you did manually)
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
