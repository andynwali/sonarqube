  node {
  stage('SCM Checkout') {
    git 'https://github.com/andynwali/sonarqube.git'
  }
  stage('SonarQube analysis') {
    def scannerHome = tool 'SonarQube_Scanner';
    withSonarQubeEnv('SonarQube') { 
      sh "${scannerHome}/bin/sonar-scanner -Dsonar.host.url= http://localhost:9000 -Dsonar.login=admin -Dsonar.projectName=aps-testProject -Dsonar.projectVersion=${env.BUILD_NUMBER} -Dsonar.projectKey=APS"
    }
  }
}
