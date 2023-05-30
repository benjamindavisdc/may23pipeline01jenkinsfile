pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                script {
                    git clone 'https://github.com/benjamindavisdc/may23pipeline01.git' temp_repo
                }
            }
        }
        
        stage('Copy Files') {
            steps {
                script {
                    sh '''
                    //Html site, doesn't need any packaging
                    docker cp temp_repo/. my-apache-container:/var/www/html/
                    '''
                }
            }
        }
        
        stage('Clean Up') {
            steps {
                sh 'rm -rf /tmp/repository'
            }
        }
    }
}
