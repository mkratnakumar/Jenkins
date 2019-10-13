pipeline{
    agent any
    environment{
        PATH="/usr/share/maven/bin:$PATH"
    }

    stages{
       stage("Git Checkout"){
            steps{
                 git credentialsId: '4007c218-5ab1-428c-96f9-227a4762439a', url: 'https://github.com/mkratnakumar/Jenkins.git'
                              
            } 
       }    
        stage("Maven Build"){
            steps{
                sh "mvn clean package"
                sh "mv target/*.war target/myweb.war"
            }
        }
        stage("deploy-dev"){
            steps{ 
                sshagent(['tomcat']) {
                   sh """
                   scp 'ssh -o StrictHostKeyChecking=no target/myweb.war ec2-user@172.31.3.230:/opt/tomcat8/webapps/
                   ssh ec2-user@172.31.3.230 /opt/tomcat8/bin/shutdown.sh
                   ssh ec2-user@172.31.3.230 /opt/tomcat8/bin/startup.sh
                   """
                }
            }
        }
    }
}
         
                   

