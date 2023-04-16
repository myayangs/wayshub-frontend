def server = 'devops@103.13.206.190'
def cred = 'appserver'
def directory = '~/wayshub-frontend'
def branch = 'main'

pipeline{
    agent any
    stages{
        stage ('git pull'){
            steps{
                sshagent([secret]) {
                    sh """ssh -o StrictHostKeyChecking=no ${server} << EOF
                    cd ${directory}
                    git pull origin ${branch}
                    exit
                    EOF"""
                }
            }
        } }
}
