
pipeline {
  agent any
  stages {
      stage('Build') {
      steps { 
          nodejs(nodeJSInstallationName: 'Node 6.x') {
              sh 'ng build'
              }
     }
    }
  }
}