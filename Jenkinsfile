pipeline {
    agent any
    //parameters {
    //   string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

    //   text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

    //   booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

    //    choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

    //    password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    //}
    triggers { pollSCM('*/1 * * * *') }
    environment {
        ENV_URL = "pipeline.google.com"
        ACCESS_KEY = credentials('AWS_ACCESS_KEY')
        SSH_CRED = credentials('ec2-user')
    }
    options {
        buildDiscarder(logRotator(numToKeepStr: '3'))
        disableConcurrentBuilds()
        timeout(time: 1, unit: 'MINUTES')
    }
    tools {
            maven 'maven-3.5.0' 
        }
    stages {
        stage('First Stage') {
            steps {
                sh "echo one" 
                sh "env"
                sh 'mvn --version'
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