pipeline {
    agent any
    options {
      lock(resource: "${env.JOB_NAME}-${env.ENVIRONMENT}")
    }	

    environment {
        PROPERTIES = readProperties file: "${WORKSPACE}/env/${ENVIRONMENT}.properties"
        AWS_DEFAULT_REGION = "us-east-2"
        AWS_ECS_CLUSTER = "${PROPERTIES.AWS_ECS_CLUSTER}"
        AWS_ECS_SERVICE = "${PROPERTIES.AWS_ECS_NGINX_SERVICE}"
        AWS_ECS_TASK_DEFINITION = "${PROPERTIES.AWS_ECS_NGINX_TASK_DEFINITION}"
        IMAGE_TAG = "${PROPERTIES.IMAGE_TAG}"
        IMAGE_BUILD_ENV = "${PROPERTIES.IMAGE_BUILD_ENV}"
    }	
    stages {
    
        stage('Checkout') {
            steps {
                script {
                    currentBuild.displayName = "#${BUILD_NUMBER} - ${ENVIRONMENT} - ${GIT_BRANCH.replace('origin/', '')}"
                    checkout scm
                }
            }
        }
        stage ('testing env'){
	  steps{
	    script {
		    echo " service name: ${AWS_ECS_SERVICE}"
		    echo " cluster name: ${AWS_ECS_CLUSTER}
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
	
