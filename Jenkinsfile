
pipeline {
  agent any
  stages {
      stage('Install') {
          steps { 
              nodejs(nodeJSInstallationName: 'Node js') {
              sh 'npm install'
              }
            }
          }

      stage('Build') {
      steps { sh 'ng build' }
     }
    }
  }
}