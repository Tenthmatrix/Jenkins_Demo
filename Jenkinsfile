pipeline {
    agent any 
    stages {
        stage('Stage 1') {

withCredentials([file(credentialsId: '', variable: 'edge_installer_properties')]) {
    // some block

echo $BITBUCKET_PRIVATE_KEY

}
            steps {
                echo 'Hello world!' 
            }
        }
    }
}

