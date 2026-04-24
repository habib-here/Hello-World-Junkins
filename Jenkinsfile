flag = true

pipeline {
    agent any
    environment {
        // variables defined here can be used by any stage
        NEW_VERSION = '1.3.0'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                // using environment variable
                // To output the value of variable in string use " "
                echo "Building version ${NEW_VERSION}"
            }
        }
        stage('Test') {
            when {
                expression {
                    flag == false
                }
            }
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }

    post {
        always  { echo 'Post build condition running' }
        failure { echo 'Post Action if Build Failed' }
    }
}

