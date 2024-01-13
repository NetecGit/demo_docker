 pipeline {
    agent { docker { image 'maven:3.3.3' } }
      stages {
        stage('Probando la integracion con docker') {
      steps {
        sh 'pwd'
        sh 'mvn --version'
        sh 'mvn clean package -DskiptTest -B -ntp'
        sh 'ls -l target/*.jar'
      }
    }
  }
}