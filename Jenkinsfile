pipeline {
    agent any
    environment {
        ENV_URL = "pipeline.google.com"
    }
    stages{
        stage('Stage One') {
            steps {
                sh '''  
                        echo Hello World
                        echo Welcome to Jenklns
                        echo Environment URL is ${ENV_URL}
                        
                    '''
            }
        }

        stage('Stage Two') {
            steps {
                sh "echo stage two demo"
            }
        }

        stage('Stage three') {
            steps {
                sh "echo Stage Three Demo"
            }
        }
    }
}
