pipeline {
    agent any
    environment {                           # Pipleline Variables: All the stages of pipline can access and use it
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
            environment {
                Batch = "b55"
            }
            steps {
                sh "echo stage two demo"
                sh "echo Training Batch is  ${Batch}"
            }
        }

        stage('Stage three') {
            steps {
                sh "echo Stage Three Demo"
            }
        }
    }
}
