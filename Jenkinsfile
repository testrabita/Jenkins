pipeline {
    agent any                                                                                                                                                                                                                                                                           stages {
        stage('Git Connect') {
steps {
                sh 'rm -Rf Jenkins'
                sh 'git clone https://github.com/testrabita/Jenkins.git'
                sh 'cd Jenkins && ls -ltr'
                }                                                                                                                                         
}
stage('Docker Image Creation')                                                                                                            
{                                                                                                                                         
steps{         
sh 'sudo docker ps'
                sh 'sudo docker images'
                sh 'sudo docker build -t rabitanginx03 .'
                sh 'sudo docker images'
                sh 'sudo docker stop rabitanginx03'
                sh 'sudo docker rm rabitanginx03'
                sh 'sudo docker run -dit --name rabitanginx03 -p8020:80 rabitanginx03'
} 
}                                                                 
 stage('Tag Image')                                                                                                                        
{                                                                                                                                        
 steps
{
               sh 'sudo docker image tag rabitanginx03 rabita/rabitanginx03:1.0'                                                               
 }
        }
    }
}    
