flag = true

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
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

