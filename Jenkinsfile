pipeline {
    agent none
   triggers {
       pollSCM '* * * * *'
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
            agent any

            steps {
                echo "Testing.."

                sh '''
                 cd myapp
                python3 hello.py
                python3 hello.py --name=Brad
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