pipeline {
    agent any
    stages {
        stage("clone code") {
            steps {
                //sh "rm -r *"
                git url: 'https://github.com/Dineshgit1996/node_cicd.git'
            }
        }
        stage("deploy"){
            steps {
                sshagent(['13.126.32.228']) {
                    sh "scp -r -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/NodejsProject/* ubuntu@13.126.32.228:/var/www/html/"
                    sh "ssh ubuntu@13.126.32.228 /var/www/html/npm.sh"
                }
            }
        }  
    }
}
