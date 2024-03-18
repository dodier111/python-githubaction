pipeline {
    agent any

    stages {
        stage('Checkout Repository') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/dodier111/python-githubaction.git']]])
            }
        }

        stage('Deploy and Run Python Application') {
            steps {
                sh 'pip3 install -r requirements.txt'
                sh 'python3 app.py'
            }
        }
    }
}

