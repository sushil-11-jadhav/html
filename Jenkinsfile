pipeline {
		agent {
			label {
					label "built-in"
					customWorkspace "/mnt/vol"
			}
		}
		stages {
			stage ("stage-1") {
				steps {
					sh "rm -rf /mnt/vol/*"
					sh "docker kill unit1"
					sh "docker system prune -a -f"
					sh "git clone https://github.com/sushil-11-jadhav/html.git -b 23Q1 /mnt/vol/23Q1"
					sh "chmod -R 777 /mnt/vol/23Q1/index.html"
					sh "docker run -dp 80:80 -v /mnt/vol/23Q1:/usr/local/apache2/htdocs --name unit1 httpd"
				}
			}
		}
}
