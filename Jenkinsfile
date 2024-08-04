pipeline {
    agent any
    environment {
        ENV_URL = "pipeline.google.com"
    }
    stages {
        stage('First Stage') {
            steps {
                echo "one"
            }
        }
        stage('Second Stage') {
            steps {
                sh "echo second"
                sh "echo ENV_URL is ${ENV_URL}"
            }
        }
        stage('Third Stage') {
            steps {
                sh 
                     '''echo aws
                      echo devops
                      echo bash'''
            }
        }
    }
}