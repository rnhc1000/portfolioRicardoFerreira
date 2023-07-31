node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    
    withSonarQubeEnv(credentialsId: 'SonarToken') {
}
    
  }
}