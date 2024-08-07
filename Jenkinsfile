pipeline {
    agent { label 'Tools_node2' }
    stages {
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
