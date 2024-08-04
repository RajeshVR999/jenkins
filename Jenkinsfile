pipeline {
    agent any
    environment {
        ENV_URL = "pipeline.google.com"
        ACCESS_KEY = credenatil('AWS_ACCESS_KEY')
    }
    stages {
        stage('First Stage') {
            steps {
                sh echo "one"
                sh "env" 
            }
        }
        stage('Second Stage') {
            steps {
                sh "echo second"
                sh "echo ENV_URL is ${ENV_URL}"
                sh "echo $ACCESS_KEY"
            }
        }
        stage('Third Stage') {
            environment {
                ENV_URL = "Stage.google.com"
            }
            steps {
                sh'''
                    echo aws
                    echo devops
                    echo bash
                    '''                          
            }
        }
    }
}