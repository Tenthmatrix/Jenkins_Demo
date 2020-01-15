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
     sh 'echo $CREDS_FILE'
//      sh 'echo "DOCKER_REGISTRY: $DOCKER_REGISTRY"'
  //    sh 'echo "$DOCKER_REGISTRY"'
//      sh 'export "MY_DOCKER_REGISTRY=$CREDS_FILE.BITBUCKET_PRIVATE_KEY"'

     sh 'echo -e "#!/bin/sh" >> /tmp/edge_nightly.sh'
     sh 'cat $CREDS_FILE >> /tmp/edge_nightly.sh'
     sh 'chmod +x /tmp/edge_nightly.sh'
     sh '/tmp/edge_nightly.sh'
     sleep 2
     sh 'rm -f /tmp/edge_nightly.sh'

    echo sh(returnStdout: true, script: 'env')
}


      }
        }

  }
}
