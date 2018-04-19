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
