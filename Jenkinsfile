pipeline {
    agent any

    stages {
        stage('Compile & Package') {
            steps {
                echo 'Compiling source code...'
                echo 'Packaging application artifact...'
            }
        }

        // Both of these test modules will execute at the exact same time
        stage('Run Parallel Automation Suites') {
            parallel {
                stage('Browser UI Tests') {
                    steps {
                        echo 'Starting Chrome and Firefox automation test suites...'
                        sleep time: 5, unit: 'SECONDS'
                        echo 'UI testing finished successfully!'
                    }
                }
                stage('Backend API Tests') {
                    steps {
                        echo 'Sending parallel integration payloads to API endpoints...'
                        sleep time: 3, unit: 'SECONDS'
                        echo 'API validation finished successfully!'
                    }
                }
            }
        }

        stage('Deploy Production') {
            steps {
                echo '🎉 Deployment complete! Application is live.'
            }
        }
    }
}
