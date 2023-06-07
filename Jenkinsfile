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
								sh "rm -rf /mnt/doc/*"
								sh "docker kill server1"
								sh "docker system prune -a -f"
								sh "git clone https://github.com/sushil-11-jadhav/html.git -b 23Q1 /mnt/doc/html/23Q1"
								sh "docker run -itdp 80:80 --name server1 httpd"
								sh "chmod -R 777 /mnt/doc/23Q1/index.html"
								sh "docker cp /mnt/doc/html/23Q1/index.html server1:/usr/local/apache2/htdocs/"
						}	
				}
				stage ("23Q2-90") {
						steps {
								sh "docker kill server2"
								sh "docker system prune -a -f"
								sh "git clone https://github.com/sushil-11-jadhav/html.git -b 23Q2 /mnt/doc/html/23Q2"
								sh "docker run -itdp 90:80 --name server2 httpd"
								sh "chmod -R 777 /mnt/doc/23Q2/index.html"
								sh "docker cp /mnt/doc/html/23Q2/index.html server2:/usr/local/apache2/htdocs/"
						}
				}
				stage ("23Q3-8081") {
						steps {
								sh "docker kill server3"
								sh "docker system prune -a -f"
								sh "git clone https://github.com/sushil-11-jadhav/html.git -b 23Q3 /mnt/doc/html/23Q3"
								sh "docker run -itdp 8081:80 --name server3 httpd"
								sh "chmod -R 777 /mnt/doc/23Q3/index.html"
								sh "docker cp /mnt/doc/html/23Q3/index.html server3:/usr/local/apache2/htdocs/"
						}
				}
		}
}
