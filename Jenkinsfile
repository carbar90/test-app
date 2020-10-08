
pipeline {
  agent any
  stages {
      stage('Build') {
      steps { 
          nodejs(nodeJSInstallationName: 'Node 12.12.0') {
              sh 'ng build'
              }
     }
    }
  }
}