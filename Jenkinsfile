pipeline {
    agent any

    stages {
        stage('Build & Test') {
            steps {
                echo 'Compiling code and running unit tests...'
                // Simulating a code failure caught during testing
                error "CRITICAL ERROR: Automated unit tests failed! Code has bugs."
            }
        }
        stage('Deploy Phase') {
            steps {
                echo 'This line will never be reached because the build failed above.'
            }
        }
    }

    // This section runs automatically after the stages finish
    post {
        always {
            echo 'Pipeline has finished running. Cleaning up workspace directories...'
        }
        failure {
            echo '🚨 ALERT: The pipeline failed! Sending emergency notification to developers.'
        }
    }
}
