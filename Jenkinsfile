pipeline {
		agent {
				label {
						label "built-in"
						customWorkspace "/mnt/doc"
				}
		}
		stages {
				stage ("23Q1-80") {
						steps {
								sh "rm -rf *"
								sh "docker run -itdp 80:80 --name "server1" httpd"
								sh "docker cp /mnt/doc/23Q1/index.html server1:/usr/local/apache2/htdocs"
						}
				}
				
		}
}
