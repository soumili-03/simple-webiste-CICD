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
                // Windows command to check if file exists
                bat 'if exist index.html (echo HTML file found) else (exit 1)'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying to web server...'
                // For demonstration, create folder and copy to a temp directory
                bat '''
                    if not exist C:\\temp\\deployed-website mkdir C:\\temp\\deployed-website
                    copy index.html C:\\temp\\deployed-website\\
                '''
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
