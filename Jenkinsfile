 pipeline {
    agent any
    stages {
        stage('gitclone') {
            steps { 
                git 'https://github.com/ArasanKavi/node.git'
                sh 'rm -rf .git'
            }
        }
        stage('Deploy') {
            steps{
             sshagent(['ssh-key']) {
                sh """
                  scp -o StrictHostKeyChecking=no -r ${env.WORKSPACE}/* root@54.144.232.205:/var/www/html/${env.JOB_BASE_NAME}
               """
                
              }
            }
        }
     }
 }
