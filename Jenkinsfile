def cred = 'appserver'
def server = '<bhq@34.143.162.86>'
def dir = '~/literature-fe'
def branch = 'main'

pipeline {
   agent any
   stages{
     stage('docker-compose'){
       steps{
          sshagent([cred]){
             sh """ssh -o  StrictHostKeyChecking=no ${server} << EOF
             cd ${dir}
             docker-compose down
             git pull origin ${branch}
             exit
             EOF"""
             }
         }
     }
 }
