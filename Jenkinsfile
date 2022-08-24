pipeline {
    agent none
    stages {
        stage('build') {
        agent {
            docker {
                image 'python:3.7.12'
            }
            input{
                message 'Press Ok to Proceed'
                parameteres {
                    string(name:'username', defaultValue: 'user', description: 'Type your username')
                }
            }
            steps {
                sh '''
                python3 -m venv .venv
                . .venv/bin/activate
                pip3 install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            agent {
                docker{
                    image 'python:3.7.12'
                }
            }
            steps {
                sh '''
                . .venv/bin/activate
                python3 test.py
                '''
            }
        }
        stage('Deploy') {
            agent any
            steps {
                sh '''
                docker --version
                echo 'Deployed Successfully!!'
                '''
            }
        }
        }
    }
}
