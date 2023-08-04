node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SONAR_SCANNER'    
    withSonarQubeEnv(credentialsId: 'SONAR_LOCAL_QG') {
	    sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
