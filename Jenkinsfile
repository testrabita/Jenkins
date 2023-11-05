pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
   
                sh 'rm -Rf Jenkins'
                sh 'git clone https://github.com/testrabita/Jenkins.git'
                sh 'cd Jenkins && ls -ltr'
                sh 'sudo docker ps'
                sh 'ls -ltr'
            }
        }
    }
}
