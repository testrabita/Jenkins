pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello Rabita'
                sh 'pwd'
                sh 'ls -ltr'
                sh 'touch a.txt'
                sh 'ls -ltr'
                sh 'rm -Rf Jenkins'
                sh 'git clone https://github.com/testrabita/Jenkins.git'
                sh 'cd Jenkins && ls -ltr'
                sh 'ls -ltr'
            }
        }
    }
}
