pipeline {
    agent any 

script{
   withCredentials([
      string(
         credentialsId: 'edge_installer_properties',
         variable: 'BITBUCKET_PRIVATE_KEY')
      ]) {
      sh """#!/bin/bash
         echo 'BITBUCKET_PRIVATE_KEY ${BITBUCKET_PRIVATE_KEY}' 
         """
  }
}

    stages {
        stage('Stage 1') {
            steps {
                echo 'Hello world!' 
            }
        }
    }
}

