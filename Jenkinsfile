pipeline {
    agent any

    stages {
        stage('Checkout Repository') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/Taissery-Suhaib/python.git']]])
            }
        }

        stage('Deploy and Run Python Application') {
            steps {
                sh 'pip3 install -r requirements.txt'
                sh 'sudo -u ubuntu /usr/local/bin/pm2 start app.py --interpreter python3'
            }
        }
    }
}


