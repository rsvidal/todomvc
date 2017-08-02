pipeline {
  agent any
  stages {
    stage('Initialize') {
      steps {
        nodejs(nodeJSInstallationName: 'node:8.2.1') {
          sh 'echo $PATH'
          sh 'npm -v'
          sh 'node -v'
          
          dir('src/webapp') {
            sh 'ls'
            sh 'npm start'
          }
        }
      }
    }
    stage('Build') {
      steps {
        sh './gradlew clean test'
      }
    }
  }
}
