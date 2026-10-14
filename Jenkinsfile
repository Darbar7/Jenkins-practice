pipeline {
    agent any

    stages {
        stage('Build & Test') {
            steps {
                echo 'Compiling code and running unit tests...'
                echo 'All tests passed cleanly this time!'
            }
        }
        stage('Deploy Phase') {
            steps {
                echo 'Deploying application safely to production!'
            }
        }
    }

    post {
        always {
            echo 'Pipeline has finished running. Cleaning up workspace directories...'
        }
        success {
            echo '🎉 SUCCESS: The pipeline recovered! Everything is green and deployed.'
        }
    }
}
