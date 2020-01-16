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
             script {
     sh 'set +x' // to debug
     echo sh(returnStdout: true, script: 'ssh -vT git@github.com')

     //sh '$CREDS'
     //sh "echo -var='project=${KAFKA_PROXY_URI}'"
        }

     //echo sh(returnStdout: true, script: 'env')
     //echo sh(returnStdout: true, script: 'ssh -vT git@github.com')

        
        }
      }
    }

  }
}