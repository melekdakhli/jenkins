pipeline {
    agent none

    triggers {
        pollSCM('* * * * *')
    }

    stages {

        stage('Build') {
            agent {
                dockerContainer {
                    image 'python:3.11'
                }
            }

            steps {
                echo "Building.."

                sh '''
                    cd myapp
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Test') {
            agent {
                dockerContainer {
                    image 'python:3.11'
                }
            }

            steps {
                echo "Testing.."

                sh '''
                    cd myapp
                    python hello.py
                    python hello.py --name=Brad
                '''
            }
        }

        stage('Deliver') {
            agent any

            steps {
                echo "Deliver...."

                sh '''
                    echo "doing delivery stuff.."
                '''
            }
        }
    }
}