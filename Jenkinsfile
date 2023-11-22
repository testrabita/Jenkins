pipeline {
    agent any                                                                                                                                                                                                                                                                
stages {
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
                sh 'sudo docker run -dit --name rabitanginx03 -p8021:80 rabitanginx03'
} 
}  
                                                               
 stage('Tag Image')                                                                                                                        
{                                                                                                                                        
 steps
{
               sh 'sudo docker image tag rabitanginx03 rabita13/rabitanginx03:1.0'                                                               
 }
        }

stage('push Image to docker Hub')
{
steps{
      sh 'sudo docker login -u=${udockerrabita} -p=${pdockerrabita} && sudo docker push rabita13/rabitanginx03:1.0'
    }
    }


    stage('kubernetes Deploy')
    {
    steps
   {
   sh 'chmod 600 jmtksrv01.pem'
   sh 'scp -i jmtksrv01.pem -o StrictHostKeyChecking=no kube01.yaml ec2-user@3.109.133.86:/home/ec2-user/'
   sh 'ssh -i jmtksrv01.pem -o StrictHostKeyChecking=no ec2-user@e3.109.133.86 "kubectl create -f kube01.yaml"'
   }
    }



}  
}  
