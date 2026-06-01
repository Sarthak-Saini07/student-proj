pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                bat 'mvn compile'
            }
        }
        stage('Test'){
            bat 'mvn test'
        }
        stage('Package'){
            bat 'mvn package'
        }
        stage ('Docker Build'){
            bat 'docker build -t myapp:v1 .'
        }
    }
    post{
        success{
            echo "Build successful"
        }
        failure{
            echo "Build is failed"
        }
        always{
            echo "pipeline completed"
        }
    }
}