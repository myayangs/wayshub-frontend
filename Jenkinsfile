def branch = "main"
def repo = "https://github.com/myayangs/wayshub-frontend.git"
def cred = "appserver"
def dir = "~/wayshub-frontend"
def server = "devops@103.37.125.64"
def imagename = "wayshub-fe"
def dockerusername = "myayangs"

pipeline {
    agent any

    stages {
        stage('Pull From Repository') {
            steps {
                sshagent([cred]) {
                    sh """ssh -o StrictHostKeyChecking=no ${server} << EOF
                        cd ${dir}
                        git remote add origin ${repo} || git remote set-url origin ${repo}
                        git pull origin ${branch}
                        exit
                        EOF
                    """
                }
            }
        }
}
}
