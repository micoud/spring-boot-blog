pipeline {
    agent any
    tools {
        maven 'ACS Maven'
        jdk 'jdk8_161'
    }
    stages {
        stage ('Initialize') {
            steps {
               echo 'Init....'
               sh '''
                  echo "M2_HOME = /jenkins/.m2"
               '''
            }
        }

        stage ('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
