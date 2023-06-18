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
                //Html site, doesn't need any packaging
                sh 'cp "/tmp/repository/*" /var/www/html/index.html'
            }
        }
        
        stage('Clean Up') {
            steps {
                sh 'rm -rf /tmp/repository'
            }
        }
    }
}
