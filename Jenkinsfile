pipeline {
    agent {label 'ws'}
    environment {                           // Pipeline Variables: All the stages of pipline can access and use it
        ENV_URL = "pipeline.google.com"     // Stage Level variables has higher priority 
        SSH_CRED = credentials('SSH_CRED')
    }

    triggers {
       pollSCM('*/59 * * * 1-5')                  //  cron('*/2 * * * 1-5')           // Cron is schedule timer to run the task regardless of changes
    }                                                                                 // pollSCM is also a scheduled timer but works only when changes occurs

    tools {
        maven 'maven-3.9.5'
    }   

    stages{
        stage('Parallel Demo') {
            parallel {
                stage('Stage One') {
                    steps {
                        sh '''  
                            echo Hello World
                            echo Welcome to Jenkins
                            echo Environment URL is ${ENV_URL}
                            mvn -v
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
    }
    post {
        always {
            clearWs()
        }
    }
}
