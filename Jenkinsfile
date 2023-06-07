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
								sh "docker cp /mnt/doc/23Q1/index.html server1:/usr/local/apache2/htdocs/"
						}
				}
				stage ("23Q2-90") {
						steps {
								sh "docker run -itdp 90:80 --name "server2" httpd"
								sh "docker cp /mnt/doc/23Q2/index.html server2:/usr/local/apache2/htdocs/"
						}
				}
				stage ("23Q3-8081") {
						steps {
								sh "docker run -itdp 8081:80 --name "server3" httpd"
								sh "docker cp /mnt/doc/23Q3/index.html server3:/usr/local/apache2/htdocs/"
						}
				}
		}
}
