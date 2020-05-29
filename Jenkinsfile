  node {
  stage('SCM Checkout') {
    git 'https://github.com/andynwali/CloudFormation.git'
  }
  stage('SonarQube analysis') {
    def scannerHome = tool name: 'SonarQube_Scanner';
    withSonarQubeEnv('SonarQube') { 
      sh "${scannerHome}/bin/sonar-scanner -Dsonar.host.url=http://ec2-52-90-56-173.compute-1.amazonaws.com -Dsonar.login=admin -Dsonar.password=admin -Dsonar.projectName=aps-test-Project -Dsonar.projectVersion=${env.BUILD_NUMBER} -Dsonar.projectKey=APS"
    }
  }
}
