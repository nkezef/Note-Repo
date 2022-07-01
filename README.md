# Note-Repo
node{
 def mavenHome = tool name: 'maven3.8.6'   
 stage('1cloneCode'){
    sh "echo running a software build and deployment project for payPal"
    git "https://github.com/LandmakTechnology/maven-web-application"
 } 
 stage('2Test&Build'){
    sh "${mavenHome}/bin/mvn install"
 } 
 /*
 stage('3CodeQuality'){
  sh "${mavenHome}/bin/mvn sonar:sonar"
 }   
 stage('4UploadArtifacts'){
  sh "${mavenHome}/bin/mvn deploy"
 } 
  stage('5deploy_uat'){
    //sh "scp "
    deploy adapters: [tomcat9(credentialsId: 'tomcatCredentials', path: '', url: 'http://18.119.10.206:8080/')], contextPath: null, war: 'target/*war'
  }
 stage('6Approval'){
    timeout(time:9, unit:'HOURS') {
        input message: 'Application ready for deployment, Please review and approve'
    }
 }
 stage('7deploy_prod'){
     deploy adapters: [tomcat9(credentialsId: 'tomcatCredentials', path: '', url: 'http://18.119.10.206:8080/')], contextPath: null, war: 'target/*war'
 }
 stage('8Notification'){
    // Pipeline Syntax 
    emailext body: '''Build status for frontend application.

Regards,
Landmark Technologies''', recipientProviders: [buildUser(), developers(), contributor()], subject: 'Build Status', to: 'paypal-team@gmail.com'
 }
*/
}  
