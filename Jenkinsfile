node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SONAR_SCANNER'    
    withSonarQubeEnv() {
	    sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
