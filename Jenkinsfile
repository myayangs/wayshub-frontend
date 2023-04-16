def server = 'devops@103.37.125.64'
def cred = 'appserver'
def directory = '~/wayshub-frontend'
def branch = 'main'

pipeline{
    agent any
    stages{
        stage ('git pull'){
            steps{
                sshagent([cred]) {
                    sh """ssh -o StrictHostKeyChecking=no ${server} << EOF
                    cd ${directory}
                    git pull origin ${branch}
                    exit
                    EOF"""
                }
            }
        } }
}
