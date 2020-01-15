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
       
  ws {
   withCredentials([file(credentialsId: 'edge_installer_properties', variable: 'CREDS_FILE')]) {
     // sh 'use $CREDS_FILE'
     sh 'echo $CREDS_FILE'
      sh 'echo "DOCKER_REGISTRY: $DOCKER_REGISTRY"'
//      sh 'export "MY_DOCKER_REGISTRY=$CREDS_FILE.BITBUCKET_PRIVATE_KEY"'
}

      echo sh(returnStdout: true, script: 'env')
  }

      }
        }

  }
}
