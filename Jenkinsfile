pipeline {
  agent any
  stages {

    stage('list credentials ids') {
      steps {
        script {
          sh 'cat $JENKINS_HOME/credentials.xml | grep "<id>"'
        }
      }
    }


    stage('Extract credentials from file') {

      steps {
       
withCredentials([file(credentialsId: 'edge_installer_properties', variable: 'CREDS')]) {
{

    sh "cp \$CREDS /tmp/creds.txt"
    sh "ls -l /tmp/creds.txt"
    sh "cat /tmp/creds.txt"

}


}


      }
        }

  }
}