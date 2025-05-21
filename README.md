# bbhartifrist
#bbhartifrist
pipeline {
    agent any
    environment {
        USER_NAME='pritesh'
        PROJECT_NAME='DEVOPS'
        PROJECT='multiple'
        TOOL='jenkins'
    }
    parameters {
  string description: 'enter your gender', name: 'UserGender'
  choice choices: ['Mail', 'female'], description: 'please select gender', name: 'selected Gender'
    }
    stages {
        stage ('checkout') {
            input {
                message "please select before checkout"
            }
            steps {
                sh '''
                    echo "${USER_NAME}"
                    echo "${TOOL}"
                    echo "${PROJECT_NAME}"
                '''

            }
        }
        stage ('test') {
            input{
                message "please select before test"
            }
            steps {
                sh 'echo "${PROJECT}"'
                sh 'echo "${BUILD_ID}"'
                
            }
        }
        stage ('build') {
            steps {
                sh 'ls'
            }
        }
    }
}
