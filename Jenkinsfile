node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SONAR_SCANNER'    S
    withSonarQubeEnv(credentialsId: 'SonarTokenPortfolio') {
	    sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
