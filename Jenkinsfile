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
        sh '''
                  echo "PATH = ${PATH}"'''
        sh 'echo "M2_HOME = ${M2_HOME}"'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn -X test'
      }
    }
  }
  tools {
    maven 'ACS Maven'
    jdk 'jdk8_161'
  }
}