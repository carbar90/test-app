
pipeline {
  agent any
  stages {
      stage('Install') {
          steps { sh 'npm install'}
          }

      stage('Build') {
          steps { sh 'ng build'}
          }

      stage('Deploy') {
          sshagent(credentials : ['centos-local']) {
              sh "ssh 192.168.1.211 'sudo systemctl stop nginx' "
              sh "ssh 192.168.1.211 'sudo systemctl status nginx' "
              sh "ssh 192.168.1.211 'rm -rf  /usr/share/nginx/html/dist' "
              sh "ssh 192.168.1.211 'mv /dist  /usr/share/nginx/html/dist' "
              sh "ssh 192.168.1.211 'sudo systemctl start nginx' "
  }
}