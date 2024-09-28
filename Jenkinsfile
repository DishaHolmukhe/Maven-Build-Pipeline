pipeline {
    agent any

    tools {
        maven 'Maven3.9.9' // Specify the Maven installation you configured
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/username/maven-project.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    sh 'mvn clean install'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh 'mvn test'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh 'mvn deploy'
                }
            }
        }
    }

    post {
        always {
            echo 'Cleaning up workspace...'
            cleanWs()  // Cleanup workspace after the build
        }
    }
}
