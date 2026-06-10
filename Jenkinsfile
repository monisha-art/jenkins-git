pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/monisha-art/jenkins-git.git'
            }
        }

        stage('Deploy to Apache') {
            steps {
                sh '''
                scp index.html ec2-user@172.31.12.196:/tmp/
                ssh ec2-user@172.31.12.196 "sudo cp /tmp/index.html /var/www/html/index.html"
                '''
            }
        }
    }
}
