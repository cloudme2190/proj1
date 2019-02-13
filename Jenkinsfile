node {
   def mvnHome
   stage('Tool Setup') { // for display purposes          
      mvnHome = tool 'mvn'
   }
   stage('checkout'){
      checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/cloudme2190/proj1.git']]])
   }
   
    stage('Build') {
      // Run the maven build
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn'  clean package"
      } else {
         bat(/"${mvnHome}\bin\mvn"  clean package/)
      }
}
