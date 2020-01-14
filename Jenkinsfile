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
       
withCredentials([file(credentialsId: 'edge_installer_properties', variable: 'DOCKER_REGISTRY')]) {
      sh 'echo "DOCKER_REGISTRY: $DOCKER_REGISTRY"'
      sh 'export "MY_DOCKER_REGISTRY=$DOCKER_REGISTRY"'
}

      echo sh(returnStdout: true, script: 'env')


      }
        }

  }
}
