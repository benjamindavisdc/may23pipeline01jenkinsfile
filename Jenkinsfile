pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/benjamindavisdc/may23pipeline01.git'
            }
        }
        
        stage('Copy Files') {
            steps {
                sh '''
                # Html site, doesn't need any packaging
                docker cp . my-apache-container:/var/www/html/
                '''
            }
        }
        
        stage('Clean Up') {
            steps {
                sh 'rm -rf .git'
            }
        }
    }
}
