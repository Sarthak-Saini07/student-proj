pipeline {

    agent any

    triggers {
    pollSCM('* * * * *')
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
    post{
        always{
            junit '**/target/surefire-reports/*.xml'
        }
    }

}