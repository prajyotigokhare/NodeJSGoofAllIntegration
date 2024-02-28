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
         snykSecurity (additionalArguments: '''snyk monitor --org="500f0e2d-6b36-446b-a7cf-3d8e99e7139b" --target-name="AllIntegration"
snyk container monitor node:latest --org="500f0e2d-6b36-446b-a7cf-3d8e99e7139b" --file=Dockerfile --target-name="AllIntegration"
snyk iac test --org="500f0e2d-6b36-446b-a7cf-3d8e99e7139b" --target-name="AllIntegration"''', failOnError: false, failOnIssues: false, projectName: 'AllIntegration', snykInstallation: 'snyk', snykTokenId: 'snykid')
        }  
         }
 }
}
