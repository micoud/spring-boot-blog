pipeline {
  agent {
    node {
      label 'sl6'
    }

  }
  stages {
    stage('Initialize') {
      steps {
        echo 'Init....'
        sh '''
                  echo "M2_HOME = /jenkins/.m2"
               '''
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }
  }
  tools {
    maven 'ACS Maven'
    jdk 'jdk8_161'
  }
}