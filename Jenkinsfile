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
                    echo "this is tes ok in branch: ${BRANCH_NAME} and env: ${ENVIRONMENT}"
		    echo "git default branch conf: ${GIT_BRANCH.replace('origin/', '')}"
                    echo "Build started with ID: ${BUILD_ID}"
                }
            }
        }
    }
}	
	
