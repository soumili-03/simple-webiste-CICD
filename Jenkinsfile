pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Validate') {
            steps {
                echo 'Validating HTML file...'
                // Simple validation - check if file exists
                sh 'test -f index.html'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying to web server...'
                // For demonstration, just copy to a temp directory
                sh 'mkdir -p /tmp/deployed-website'
                sh 'cp index.html /tmp/deployed-website/'
                echo 'Successfully deployed to temporary location'
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
    }
}
