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
    stage('Test/Build') {
      parallel {
        stage('Backend Test') {
          steps {
            echo 'Running Tests (maven)'
            sh 'mvn  test'
          }
        }
        stage('Frontend Test') {
          steps {
            sh '''echo "Frontend test"
'''
          }
        }
        stage('Build') {
          steps {
            sh 'mvn compile'
          }
        }
      }
    }
    stage('Analyze') {
      steps {
        echo 'Running Code Analysis (sonarqube)'
        sh 'sonar-scanner -Dsonar.projectKey=${SONAR_PROJECT_KEY} -Dsonar.sources=${SONAR_SOURCES} -Dsonar.java.binaries=${SONAR_JAVA_BINARIES}'
      }
    }
  }
  tools {
    maven 'ACS Maven'
  }
  environment {
    SONAR_PROJECT_KEY = 'TEST-spring-boot-blog'
    SONAR_JAVA_BINARIES = './target'
  }
}