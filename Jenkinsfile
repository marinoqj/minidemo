pipeline {
  agent any
  tools {
    maven 'mvn-3.6.3'
  }
  stages {  
    stage('SonarQube analysis') {
      steps {
        withSonarQubeEnv(installationName: 'SonarQube') {
            sh 'mvn clean compile package sonar:sonar -DskipTests -Dsonar.dependencyCheck.jsonReportPath=target/dependency-check-report.json -Dsonar.dependencyCheck.xmlReportPath=target/dependency-check-report.xml -Dsonar.dependencyCheck.htmlReportPath=target/dependency-check-report.html -Dsonar.token=squ_0511f9b91128a4f35853341c4ee36311d00b6d1b'
        }
      }      
    }   
  }
}
