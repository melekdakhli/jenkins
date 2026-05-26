pipeline {
    agent none
   triggers {
       pollSCM '*/2 * * * *'
   }
    stages {

        stage('Build') {
            agent any

            steps {
                echo "Building.."

                sh '''
                    echo "doing build stuff.."
                '''
            }
        }

        stage('Test') {
            agent any

            steps {
                echo "Testing.."

                sh '''
                    echo "doing test stuff.."
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