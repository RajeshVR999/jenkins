pipeline {
    agent any
    stages {
        stage('First Stage') {
            steps {
                echo "one"
            }
        }
        stage('Second Stage') {
            steps {
                echo "second"
            }
        }
        stage('Third Stage') {
            steps {
                sh '''echo aws
                      echo devops
                      echo bash'''
            }
        }
    }
}