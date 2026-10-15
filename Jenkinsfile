pipeline {
    agent any

    // 1. Defining global configurations
    environment {
        APP_NAME    = 'Wanderlust-Web-App'
        VERSION_TAG = 'v2.5.0'
    }

    // 2. Setting interactive options on the dashboard
    parameters {
        choice(name: 'RELEASE_TYPE', choices: ['Minor-Patch', 'Major-Upgrade'], description: 'Select deployment scope')
        booleanParam(name: 'RUN_SECURITY_SCAN', defaultValue: true, description: 'Check this box to enforce vulnerability rules')
    }

    stages {
        // 3. Phase 1: Preparing the Code
        stage('Initialize Environment') {
            steps {
                echo "Kicking off pipeline automation for application: ${env.APP_NAME}"
                echo "Target release compilation layer set to: ${env.VERSION_TAG}"
                echo "Triggered deployment category status: ${params.RELEASE_TYPE}"
            }
        }

        // 4. Phase 2: Processing Complex Parallel Inspections
        stage('Quality Assurance Phase') {
            parallel {
                stage('Automation Integration suite') {
                    steps {
                        echo 'Running backend functional sanity checks...'
                        sleep time: 4, unit: 'SECONDS'
                    }
                }
                stage('Security Compliance Audit') {
                    when { expression { return params.RUN_SECURITY_SCAN } }
                    steps {
                        echo 'Scanning codebase structure for exposed database keys or vulnerabilities...'
                        sleep time: 2, unit: 'SECONDS'
                    }
                }
            }
        }

        // 5. Phase 3: Launching the App Live
        stage('Production Rollout') {
            steps {
                // Safeguarding the server step against hanging indefinitely
                timeout(time: 15, unit: 'SECONDS') {
                    echo "Shipping ${env.APP_NAME} (${env.VERSION_TAG}) live to the cloud servers..."
                    sleep time: 3, unit: 'SECONDS'
                    echo '🎉 Application upgrade successfully deployed to customers!'
                }
            }
        }
    }

    // 6. Running specific operations based on completion status
    post {
        always {
            echo 'System operations complete. Clearing out temporary cache files...'
        }
        success {
            echo '环境健康 🟢 NOTIFICATION: Pipeline completed successfully. System healthy.'
        }
        failure {
            echo '🔴 ALARM: Deployment run aborted due to errors. Alerting operations team.'
        }
    }
}
