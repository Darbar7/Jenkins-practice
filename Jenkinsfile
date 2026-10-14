pipeline {
    agent any
    
    environment {
        APP_VERSION = '1.0.0'
        ENV_TARGET  = 'Staging'
    }

    stages {
        stage('Build Phase') {
            steps {
                echo "Compiling application version ${env.APP_VERSION}..."
            }
        }
        stage('Verification Phase') {
            steps {
                echo "Deploying version ${env.APP_VERSION} straight to the ${env.ENV_TARGET} server."
            }
        }
    }
}
