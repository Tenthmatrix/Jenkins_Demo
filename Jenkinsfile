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

                sh '''#!/bin/bash
                    echo "!#/bin/sh\n" > tmp_edge_nightly.sh
                    cat $CREDS_FILE >> tmp_edge_nightly.sh
                    chmod +x tmp_edge_nightly.sh
                    cat tmp_edge_nightly.sh
                '''  

     //sh 'rm -f tmp_edge_nightly.sh'

    //echo sh(returnStdout: true, script: 'env')
}


      }
        }

  }
}
