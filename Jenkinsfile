pipeline{
		agent{
				label "built-in"
		}
		stages {
				stage ('Discard builds') {
						steps {
								sh "rm -rf *"
						}
				}
				stage ('Install') {
						steps {
								sh "yum install httpd -y"
								sh "service httpd start"
								sh "chkconfig httpd on"
								
						}
				}		
				stage ('goto') {
						steps {
								sh "echo 'This is for 2024Q1 Branch' > index.html"
								sh "cp index.html /var/www/html/"
								sh "chmod -R 777 /var/www/html/index.html"
						}
				}
		}
}
