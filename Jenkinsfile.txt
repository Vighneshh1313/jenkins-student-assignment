pipeline {

    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Compiling application...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests... Pass!'
            }
        }

        stage('Package') {
            steps {
                sh 'echo "Build executed successfully" > build-info.txt'
            }
        }

    }

    post {

        success {
            echo 'Build successful! Ready for release.'
        }

    }

}