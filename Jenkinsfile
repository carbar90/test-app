
pipeline {
  agent any
  stages {
      stage('Build') {
      steps { 
          nodejs(nodeJSInstallationName: 'Node 12.19.0') {
              sh 'ng build'
              }
     }
    }
  }
}