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
        echo 'Running Tests (maven)'
        sh 'mvn  test'
      }
    }
    stage('Analyze') {
      steps {
        echo 'Running Code Analysis (sonarqube)'
        }
      }
    }
  
  tools {
    maven 'ACS Maven'
    jdk 'jdk8_161'
  }
}
