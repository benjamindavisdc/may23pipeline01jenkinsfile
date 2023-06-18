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
                    sh "sudo rm -rf /var/www/html/*"
                }
            }
        }

        stage('Copy Files') {
            steps {
                script {
                    sh "sudo cp -r temp_repo/. /var/www/html/"
                }
            }
        }

        stage('Clean Up') {
            steps {
                sh 'rm -rf temp_repo'
            }
        }
    }
}
