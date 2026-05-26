pipeline {
    agent none

    triggers {
        pollSCM('* * * * *')
    }

    stages {

        stage('Build') {
                agent any

            steps {
                echo "Building.."

                sh '''
                    cd myapp
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Test') {
           

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