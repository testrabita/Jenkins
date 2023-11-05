pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
   
                sh 'rm -Rf Jenkins'
                sh 'git clone https://github.com/testrabita/Jenkins.git'
                sh 'cd Jenkins && ls -ltr'
                sh 'sudo docker ps'
                sh 'sudo docker images'
                sh 'sudo docker stop rabitanginx03'
                sh 'sudo docker rm rabitanginx03'
                sh 'sudo docker build -t rabitanginx03 .'
                sh 'sudo docker run -dit --name rabitanginx03 -p8021:80 rabitanginx03'
                sh 'sudo docker images'

            }
        }
    }
}
