  node{
   stage('SCM Checkout'){
     git 'https://github.com/reachsatyabrata/my-app'
   }
   stage('Compile-Package'){
    
      def mvnHome =  tool name: 'mvn', type: 'maven'   
      sh "${mvnHome}/bin/mvn package"
   }
   stage('Email Notification'){
      mail bcc: '', body: '''Hi Welcome to jenkins email alerts
      Thanks
      Hari''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'hari.kammana@gmail.com'
   }
   stage('Slack Notification'){
       slackSend baseUrl: 'https://hooks.slack.com/services/',
       channel: '#jenkins-pipeline-demo',
       color: 'good', 
       message: 'Welcome to Jenkins, Slack!', 
       teamDomain: 'reachsatyabrata',
       tokenCredentialId: 'slack-demo'
   }
}


