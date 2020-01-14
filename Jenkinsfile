pipeline {
  agent any
  stages {
      ', 
    stage('Extract credentials') {
      steps {
        script {
          withCredentials([
            dockerCert(
              credentialsId: 'edge_installer_properties',
              variable: 'EGDE_PROPERTIES_PATH')
          ]) {
            print 'EGDE_PROPERTIES_PATH=' + EGDE_PROPERTIES_PATH
          }
        }
      }
    }

    stage('list credentials ids') {
      steps {
        script {
          sh 'cat $JENKINS_HOME/credentials.xml | grep "<id>"'
        }
      }
    }

  }
}
