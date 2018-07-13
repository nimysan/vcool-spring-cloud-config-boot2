// Jenkinsfile (Declarative Pipeline)
pipeline {
  agent any 
  def mvnHome
  stages {
   stage('show env') {
    echo "i am here"   
   }
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      git 'https://github.com/nimysan/vcool-spring-cloud-config-boot2.git'
      // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.           
      mvnHome = tool 'M3'
   }
    stage('Build') {
      // Run the maven build
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package dockerfile:build"
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      }
    }
  }
}
