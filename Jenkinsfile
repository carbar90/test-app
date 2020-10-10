
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
          steps {
          sshagent(credentials : ['centos-local']) {
              sh "ssh -o StrictHostKeyChecking=no root@192.168.1.211 'sudo systemctl stop nginx' "
              sh "ssh -o StrictHostKeyChecking=no root@192.168.1.211 'rm -rf /usr/share/nginx/html/dist' "
              sh "scp -r dist root@192.168.1.211:/usr/share/nginx/html "
              sh "ssh -o StrictHostKeyChecking=no root@192.168.1.211 'sudo systemctl start nginx' "
/*              sh "ssh root@192.168.1.211 'sudo systemctl status nginx' "
              sh "ssh root@192.168.1.211 'rm -rf  /usr/share/nginx/html/dist' "
              sh "ssh root@192.168.1.211 'mv /dist  /usr/share/nginx/html/dist' "
              sh "ssh root@192.168.1.211 'sudo systemctl start nginx' " */
          } 
      }
      }
  }
}