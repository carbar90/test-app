
pipeline {
  agent any
  stages {

      stage('Build') {
          steps { 
              nodejs(nodeJSInstallationName: 'Node js') {
                  sh 'npm install'
                  sh 'ng build'
              }
            }
          }
  }
}