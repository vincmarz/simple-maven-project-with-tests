node {
    checkout scm
    stage('Build') {
      withMaven(maven: 'M3'){
        if (isUnix()) {
          sh 'mvn -Dmaven.test.failure.ignore clean package'
        }
        else {
          echo 'No maven for Windows host'
        }
      }
    }
  stage('Resuls') {
    junit '**/target/surefire-reports/TEST-*.xml'
    archive 'target/*.jar'
  }    
}
