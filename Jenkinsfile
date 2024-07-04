pipeline {
    agent any
	

    stages {
    
        stage('Checkout') {
            steps {
                script {
                    currentBuild.displayName = "#${BUILD_NUMBER} - ${ENVIRONMENT} - ${GIT_BRANCH.replace('origin/', '')}"
                    checkout scm
                }
            }
        }

        stage('Building image') {
            steps {
                script {
                    echo "this is tes ok in branch: ${BRANCH_NAME} and ${ENVIRONMENT}"
                    echo "Build started with ID: ${BUILD_ID}"
                }
            }
        }
    }
}	
	
