pipeline {
    agent any
    environment {
        BASE_DIR_PATH = credentials('base-dir-path')
    }
    stages {
        stage('Update Repository') {
            steps {
                dir("${BASE_DIR_PATH}") {
                    sh 'git pull origin main'
                }
            }
        }
        stage('Restart Tomcat') {
            steps {
                sh 'sudo systemctl restart tomcat'
            }
        }
    }
}
