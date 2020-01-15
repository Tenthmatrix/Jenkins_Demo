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


    stage('Extract credentials') {

      steps {
       
withCredentials([file(credentialsId: 'edge_installer_properties', variable: 'CREDS_FILE')]) {

sh '''
set +x
echo "My secret is $CREDS_FILE"'
echo sh(returnStdout: true, script: "env")
'''
}


      }
        }

  }
}
