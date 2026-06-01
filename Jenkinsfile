pipeline {

    agent any

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
    triggers {
    pollSCM('H/1 * * * *')
}
    post {

        success {
            echo 'Build successful'
        }

        failure {
            echo 'Build failed'
        }

        always {
            echo 'Pipeline completed'
        }

    }

}