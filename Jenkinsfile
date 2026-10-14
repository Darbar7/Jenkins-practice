pipeline {
    agent any

    environment {
        // This safely binds your Jenkins secret string to a local variable name
        DB_PASSWORD = credentials('my-database-token')
    }

    stages {
        stage('Connect to Database') {
            steps {
                echo 'Initializing environment connections...'
                // Jenkins will automatically mask the secret text in logs!
                echo "Attempting database login using authentication key: ${DB_PASSWORD}"
            }
        }
        stage('Database Operations') {
            steps {
                echo 'Successfully authenticated! Executing migration scripts...'
            }
        }
    }
}
