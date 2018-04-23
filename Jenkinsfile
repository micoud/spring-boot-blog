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
        sh 'sonar-scanner -Dsonar.projectKey=${SONAR_PROJECT_KEY} -Dsonar.sources=${SONAR_SOURCES}'
        }
      }
    }

  environment {
    SONAR_PROJECT_KEY = "TEST spring-boot-blog"
    SONAR_SOURCES = "./src"
  }

  tools {
    maven 'ACS Maven'
    jdk 'jdk8_161'
  }
}
