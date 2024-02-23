pipeline {
 agent any
   tools {
     nodejs 'v14.21.3'
  }
stages {
 stage('check'){
steps {
git branch: 'main', credentialsId: '123', url: 'https://github.com/prajyotigokhare/nodejs-goof.git'
 }
   }
stage('build'){
  steps {
     sh 'npm install'
  }
  }
  stage('Test') {
        steps {
             snykSecurity( failOnError: false, failOnIssues: false, monitorProjectOnBuild: false, snykInstallation: 'snyk', snykTokenId: 'snykid' )
           }  
         }
 }
}

//}}}}}
