pipeline {
		agent {
				label {
						label "built-in"
						customWorkspace "/mnt/23Q1"
				}
		}
		stages {
				stage ("23Q1-80") {
						steps {
								sh "docker run -itdp 80:80 --name server1 httpd"
								sh "chmod -R 777 /mnt/23Q1/index.html"
								sh "docker cp /mnt/23Q1/index.html server1:/usr/local/apache2/htdocs"
						}
				}
				
		}
}
