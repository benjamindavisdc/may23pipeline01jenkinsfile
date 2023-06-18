pipeline {
    agent any
    stages {
        stage("Clone Git Repository") {
            steps {
                dir('temp_repo') {
                    git(
                        url: "https://github.com/benjamindavisdc/may23pipeline01.git",
                        branch: "main"
                    )
                }
            }
        }
        
        stage('Clean Web Directory') {
            steps {
                script {
                    sh '''
                    # Remove all files from the Apache web directory
                    sh rm -rf /var/www/html/*
                    '''
                }
            }
        }
        
        stage('Copy Files') {
            steps {
                //Html site, doesn't need any packaging
                sh 'cp "/tmp/repository/html portfolio template.html" /var/www/html/index.html'
            }
        }
        
        stage('Clean Up') {
            steps {
                sh 'rm -rf temp_repo'
            }
        }
    }
}




