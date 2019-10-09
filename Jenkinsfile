node{
   stage('SCM Checkout') {
     git 'https://github.com/mkratnakumar/Jenkins.git'
    }
  stage('Compile=Package'){
    def mvnHome = tool name: 'mvn', type: 'maven3'
    sh "${mvnHome}/bin/mvn package"
  }
}
