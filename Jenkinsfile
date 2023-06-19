pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                dir('temp_repo') {
                    git(
                        url: "https://github.com/benjamindavisdc/may23pipeline01.git",
                        branch: "main"
                    )
                }
            }
        }
        
        stage('Copy Files') {
            steps {
                sh 'sudo cp -R temp_repo/. /var/www/html/apache-flask/'
                sh 'sudo cp /var/www/html/apache-flask/apache-flask.conf /etc/httpd/conf.d/apache-flask.conf'
            }
        }
        
        stage('Clean Up') {
            steps {
                sh 'rm -rf /tmp/repository'
            }
        }
    }
}
