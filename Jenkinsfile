node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SONAR_SCANNER'
    withSonarQubeEnv(credentialsId: 'SonarTokenPortfolio') {
	    sh "${scannerHome}/bin/sonar-scanner"
    }
  }
  stage('Quality Gate Analysis') {

    waitForQualityGate abortPipeline: false, credentialsId: 'SonarTokenPortfolio'
  }
}
