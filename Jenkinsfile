pipeline {
    agent any
    
    // Defines global environment variables accessible by all stages
    environment {
        APP_NAME = 'GradeBookApp'
        APP_VERSION = '1.0.0'
    }
    
    stages {
        stage('Checkout') {
            steps {
                // Configured with your exact custom repository link
                git branch: 'main', url: 'https://github.com/Nxndzz/Custom-Environment-Variables-Pipeline-.git'
            }
        }
        
        stage('Show App Info') {
            steps {
                // Accessing the variables using the env object context
                echo "Building ${env.APP_NAME}, version ${env.APP_VERSION}"
            }
        }
        
        stage('Build') {
            steps {
                bat 'python -m py_compile app.py'
                echo "${env.APP_NAME} version ${env.APP_VERSION} compiled successfully."
            }
        }
    }
}
