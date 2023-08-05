pipeline {
  agent any 
  stages {
    stage('SCM') {
      steps {
        checkout scm
      }
    }
    stage('SonarQube Analysis') {
      steps {
        scannerHome = tool 'SONAR_SCANNER'
        withSonarQubeEnv(credentialsId: 'SonarTokenPortfolio') {
	      sh "${scannerHome}/bin/sonar-scanner"
        }
      }
    }
    stage('Quality Gate Analysis') {
      steps {
          waitForQualityGate abortPipeline: true, credentialsId: 'SonarTokenPortfolio'
      }
    }
  }
}
