pipeline {
    agent {
        label 'docker-agent-alpine'
    }
    stages {
        stage('Build') {
            steps {
                sh '''
                    cd myapp
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''
                    cd myapp
                    . venv/bin/activate
                    # Add your test commands here, e.g.:
                    python hello.py
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver stage (add your deployment steps)'
            }
        }
    }
}