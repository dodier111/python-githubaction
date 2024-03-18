pipeline {
    agent any
    
    environment {
        PYTHON_VERSION = '3.9'
    }
    
    stages {
        stage('Checkout') {
            steps {
                checkout()
            }
        }
        
        stage('Set up Python') {
            steps {
                script {
                    // Set up Python using actions/setup-python
                    sh "python${PYTHON_VERSION} -m venv venv"
                    sh "source venv/bin/activate"
                }
            }
        }
        
        stage('Install dependencies') {
            steps {
                // Install dependencies
                sh "pip3 install -r requirements.txt"
            }
        }
        
        stage('Deploy and Run Python Application') {
            steps {
                // Deploy and run the Python application using PM2
                sh "/usr/bin/node /usr/local/bin/pm2 start app.py --interpreter python3"
            }
        }
    }
}
