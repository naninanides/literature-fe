def cred = 'appserver'
def server = '<bhq@34.143.162.86>'
def dir = '~/literature-fe'
def branch = 'main'

pipeline {
   agent any
   stages{
     stage('docker-compose and pulling repo'){
       steps{
          sshagent([cred]){
             sh "ssh -o StrictHostKeyChecking=no ${server} 'cd ${dir} && docker-compose down && git pull origin ${branch}'"
             }
         }
      }
   stage('starting app'){
       steps{
          sshagent([cred]){
             sh "ssh -o StrictHostKeyChecking=no ${server} 'cd ${dir} && docker-compose up -d && git push origin ${branch}'"
             }
         }
      }
   }
}
