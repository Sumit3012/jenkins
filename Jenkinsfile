pipeline {
    agent any
    triggers{
        pollSCM '*/5 * * * *'
      }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                cd my-app
                pip3 install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                cd my-app
                python3 hello.py
                python3 hello.py --name=Sum
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
