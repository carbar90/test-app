
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
          steps { 
              nodejs(nodeJSInstallationName: 'Node js') {
              sh 'ng build'
              }
            }
          }
  }
}