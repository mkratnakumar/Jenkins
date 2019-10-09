node{
   stage('SCM Checkout') {
     git 'https://github.com/mkratnakumar/Jenkins.git'
    }
  stage('Compile=Package'){
    def mvnHome = tool name: 'maven', type: 'maven'
    sh "${mvnHome}/usr/share/maven  package"

  }
}
