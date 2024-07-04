pipeline {
    
    options {
        timeout(time: 60, unit: 'MINUTES')
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
                    sh "aws --version"
                }
            }
        }

        stage('Building image') {
            steps {
                script {
                    echo "this is tes ok in branch: env.BRANCH_NAME and env.ENVIRONMENT"
                    echo "Build started with ID: ${BUILD_ID}"
                }
            }
        }
    }
}	
	
