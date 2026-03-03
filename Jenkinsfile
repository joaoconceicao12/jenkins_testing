pipeline {
    agent {
        docker { image 'python:3.11' }
    }
    triggers {
        pollSCM '* * * * *'
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
                    # run your tests here, e.g.:
                    python hello.py
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}