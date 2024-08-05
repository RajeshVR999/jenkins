 pipeline {
     agent any

     options {
         ansiColor('xterm')
     }
     environment {
         SSH_CRED = credentials('SSH-CRED')
     }
     //tools {
     //    maven 'Maven' 
      //   }
     stages {
         stage('Build') {
             steps {
                sh 'mvn package'
            }
        } 
         stage('Performing Lint Checks') {
             steps {
                 sh "mvn cleanup"
                 sh "env"
                 sh "This stage should only run against the feature branch only"
                 sh "echo LINT CHECKS COMPLETED"
             }
         }
        
         stage('Performing Ansible Dryrun') {
                 steps {
                    sh "This stage should run only from the PR"
                    sh "ansible-playbook robot-dryrun.yml -e COMPONENT=mongodb -e ENV=dev -e ansible_user=${SSH_CRED_USR} -e ansible_password=${SSH_CRED_PSW}"
                 }
             }

         stage('Performing Merge') {
             steps {
                  sh "This stage should run only from the main branch"
                 sh "echo Performing Merge"
                 sh "echo Doing Deployment"
                 }
             }

         }    
     }










// // pipeline {
// //     /* Declarative Pipeline */
// // }



// // node {
// //     /* scripted pipeline */
// // }