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
       
withCredentials([file('edge_installer_properties': 'S3_ENDPOINT', variable: 'MY_S3_ENDPOINT'),
                 file('edge_installer_properties': 'DOCKER_REGISTRY', variable: 'MY_DOCKER_REGISTRY')]) {
      sh 'echo "MY_S3_ENDPOINT: $MY_S3_ENDPOINT"'
}


      }
        }

  }
}
