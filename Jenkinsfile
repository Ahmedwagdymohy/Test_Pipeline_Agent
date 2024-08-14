pipeline {
    agent any
    stages {
        stage('Build') {
            when {
                expression { 
                    return env.BRANCH_NAME == 'main' || env.BRANCH_NAME == 'dev'
                }
            }
            steps {
                echo 'Building...'
                // Your build commands, e.g., sh 'make build'
            }
        }
        
        stage('Test') {
            when {
                expression { 
                    return env.BRANCH_NAME == 'main' || env.BRANCH_NAME == 'dev'
                }
            }
            steps {
                echo 'Testing...'
                // Your test commands, e.g., sh 'make test'
            }
        }
        
        stage('Run') {
            when {
                expression { 
                    return env.BRANCH_NAME == 'main' || env.BRANCH_NAME == 'Integ'
                }
            }
            steps {
                echo 'Running...'
                // Your run commands, e.g., sh 'make run'
            }
        }
        
        stage('Integration Testing') {
            when {
                expression { 
                    return env.BRANCH_NAME == 'main' || env.BRANCH_NAME == 'Integ'
                }
            }
            steps {
                echo 'Integration Testing...'
                // Your integration test commands, e.g., sh 'make integration-test'
            }
        }
        
        stage('Reporting') {
            when {
                expression { 
                    return env.BRANCH_NAME == 'main' || env.BRANCH_NAME == 'Integ'
                }
            }
            steps {
                echo 'Reporting...'
                // Your reporting commands, e.g., sh 'make report'
            }
        }
    }
}
