pipeline {
    agent { label 'Tools2' }
    stages {
        stage('Check for Changes') {
            steps {
                script {
                    // Run git command to get changed files
                    def changes = sh(script: 'git diff --name-only HEAD~1 HEAD', returnStdout: true).trim()

                    // Check if the specific C files are in the list of changed files
                    env.RUN_SW_UNIT_1 = ( changes.contains('sum.c') || changes.contains('sumTest.cpp') ) ? 'true' : 'false'
                    env.RUN_SW_UNIT_2 = ( changes.contains('mul.c') || changes.contains('mulTest.cpp') ) ? 'true' : 'false'

                }
            }
        }
        
        stage('Build') {
            steps {
                
                echo 'Building...'
                sh 'gcc -o ahmed main.c'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // Your test commands, e.g., sh 'make test'
            }
        }
         stage('Run') {
            steps {
                echo 'Testing...'
                sh './ahmed'
            }
        }
    }
}
