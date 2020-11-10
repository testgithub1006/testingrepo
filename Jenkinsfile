
  
node {
    stage('Preparation') { 
    
    sh 'echo preparing'
    }
  
  stage("Build Image"){

   def antHome = tool name: 'ant', type: 'ant'
    
    sh "echo Logged in user is : ${USER}"
    sh 'java -version'
    sh "echo 1...antHome = ${antHome}"
   // sh 'export JAVA_HOME = /etc/alternatives/java'
    sh "echo JAVA_HOME ${JAVA_HOME}"
  
  
  }
}
