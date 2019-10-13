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
            }
        }
    }
   
}
