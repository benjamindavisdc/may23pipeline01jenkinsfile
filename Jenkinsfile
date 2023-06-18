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
                sh 'cp temp_repo/. /var/www/html/
            }
        }
        
        stage('Clean Up') {
            steps {
                sh 'rm -rf /tmp/repository'
            }
        }
    }
}
