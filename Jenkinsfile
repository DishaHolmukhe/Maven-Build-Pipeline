pipeline {
    agent any

    tools {
        maven 'Maven3.9.9' // Specify the Maven installation you configured
    }

    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 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 , url: 'https://github.com/DishaHolmukhe/Maven-Build-Pipeline.git'
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
