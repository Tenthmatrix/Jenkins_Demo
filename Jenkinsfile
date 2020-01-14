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
       
      // Using the VAR environment variable (see below)
      echo "In any Jenkins command: $VAR"
    environment {
        VAR     = credentials('edge_installer_properties')
    }

      script {
          println "Directly in Groovy:" + VAR_CHARTMUSEUM_USER
      }
      
      sh 'echo "Or in a shell $VAR_CHARTMUSEUM_USER"'

      }
        }

  }
}

