pipeline {

    agent any

    triggers {
        pollSCM('H/1 * * * *')
    }

    stages {

        stage('Build') {
            steps {
                bat 'mvn compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t myapp:v1 .'
            }
        }

    }

}