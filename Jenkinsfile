pipeline {
    agent any
    
    stages { 
        stage('Clean Up1') {
            steps {
                sh 'rm -rf temp_repo/'
            }
        }
        
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
                sh 'cp -Ru temp_repo/. /var/www/html/apache-flask/'
                sh 'cp --update /var/www/html/apache-flask/apache-flask.conf /etc/httpd/conf.d/apache-flask.conf'
            }
        }
        
        stage('Clean Up2') {
            steps {
                sh 'rm -rf temp_repo/'
            }
        }
    }
}
