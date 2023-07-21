pipeline {
	agent {
		label {
			label 'master'
			customWorkspace '/mnt/jenkins-assignment1'
		}
	}
	stages {
		stage ('Clean Workspace') {
			steps {
				cleanWs()
			}
		}
		
		stage ('deploy main branch on master') {
			steps {
				sh 'sudo yum install httpd -y'
				sh 'service httpd start'
				sh 'cp -r /mnt/jenkins-assignment1/index.html /var/www/html'
				sh 'chmod -R 777 /var/www/html'
			}
		}
		
		stage ('deploy 23q1 branch on slave-1') {
		  
			agent {
				label {
					label 'slave1'
				}
			}
			steps {
				sh 'sudo yum install httpd -y'
				sh 'service httpd start'
				sh 'cp -r /mnt/jenkins-assignment1/index.html /var/www/html'
				sh 'chmod -R 777 /var/www/html'
			}
		}
	}
}
