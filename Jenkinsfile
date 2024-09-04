pipeline {
    agent {
        docker {
            image 'python:3.8-slim-buster'
            args '-u 0:0 -v /tmp:/root/.cache'
        }
    }
    stages {
        stage("Test") {
            steps {
                sh "pip install poetry"
                sh "poetry install"
                sh "poetry run pytest"
            }
        }
    }
    post {
        success {
            echo "SUCCESSFUL"
        }
        failure {
            echo "FAILED"
        }
    }
}
