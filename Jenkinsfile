def cred = 'appserver'
def server = '<bhq@34.143.162.86>'
def dir = '~/literature-fe'
def branch = 'main'

pipeline{
   agent any
   stages{
      stage('login server'){
         steps{
            sshagent(credentials:['appserver']){
               sh 'ssh  -o StrictHostKeyChecking=no  ~/literature-fe/SSHkey.pub bhq@35.247.167.181 uptime "whoami"'
          }
        echo "success lgoin"
         }
       }
   }
}
