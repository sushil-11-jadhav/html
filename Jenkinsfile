pipeline {

		stages {
			stage ("stage-1") {
			agent {
				label {
					label "built-in"
					customWorkspace "/mnt/vol"
				}
			}
				steps {
					sh "service docker start"
					sh "rm -rf /mnt/vol/*"
					sh "docker kill unit1"
					sh "docker system prune -a -f"
					sh "git clone https://github.com/sushil-11-jadhav/html.git -b 23Q1 /mnt/vol/23Q1"
					sh "chmod -R 777 /mnt/vol/23Q1/index.html"
					sh "docker run -dp 80:80 -v /mnt/vol/23Q1:/usr/local/apache2/htdocs --name unit1 httpd"
				}
			}
			stage ("stage-2") {
				agent {
					label "slave1"
					customWorkspace "/mnt/1st"
				}
				steps {
					sh "service docker start"
					sh "rm -rf /mnt/1st/*"
					sh "docker kill unit2"
					sh "docker system prune -a -f"
					sh "git clone https://github.com/sushil-11-jadhav/html.git -b 23Q2 /mnt/1st/23Q2"
					sh "chmod -R 777 /mnt/1st/23Q2/index.html"
					sh "docker run -dp 80:80 -v /mnt/1st/23Q2:/usr/local/apache2/htdocs --name unit2 httpd"
		}
}
