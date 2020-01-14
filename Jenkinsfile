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
           environment {
      VAR = credentials("edge_installer_properties")
   }

      steps {
       
      // Using the VAR environment variable (see below)
      echo "In any Jenkins command: $VAR"

      script {
          println "Directly in Groovy:" + VAR
      }
      sh 'echo "Or in a shell $VAR"' // Careful with the semantics of ' and " here
      sh 'echo "S3_ENDPOINT: ${env.S3_ENDPOINT}"' // S3_ENDPOINT should be outputted in console


}
        }

  }
}
