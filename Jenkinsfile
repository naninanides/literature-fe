def credentials = 'appserver'
def server = '<bhq@34.143.162.86>'
def dir = '~/literature-fe'
def sshkey = 'SSHkey.pub'
def branch = 'main'

pipeline{
   agent any
   stages{
      stage('login server'){
         steps{
            sshagent(credentials:['appserver']){
               sh 'ssh -o StrictHostKeyChecking=no -i ${sshkey} bhq@35.247.167.181 uptime "whoami"'
           }
        echo "success lgoin"
         }
       }
   }
}
