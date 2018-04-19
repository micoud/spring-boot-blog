pipeline {
  agent {
    node {
      label 'SL6'
    }

  }
  stages {
    stage('Initialize') {
      steps {
        echo 'Init....'
        sh 'echo "PATH = ${PATH}"'
        sh 'echo "M2_HOME = ${M2_HOME}"'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn  test'
      }
    }
    stage('Analyze') {
      steps {
        def scannerHome = tool 'sonarqube scanner'
        withSonarQubEnv('sonarqube') {
          sh "/jenkins/sonar-scanner/bin/sonar-scanner"
        }
      }
    }
  }
  tools {
    maven 'ACS Maven'
    jdk 'jdk8_161'
  }
}
