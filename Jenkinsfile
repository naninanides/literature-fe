def cred = 'appserver'
def server = '<bhq@34.143.162.86>'
def dir = '~/literature-fe'
def branch = 'main'

pipline{
	agent any
	post {
	   always{
	     echo 'build'
	stages{
	   stage ('docker-compose'){
	       steps{
	           sshagent([cred])
	              sh """ssh -o StrictHostKeyChecking=no ${server} << EOF
	              docker-compose up
	              cd ${dir}
	              git pull origin ${branch}
	              exit
	              EOF"""
	             }
	           }  
	       }
	   }
	}
}

