pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'pip3 install ./flaskr --break-system-packages'
            }
        }
        stage('Test') {
            steps {
                sh 'pip3 install pytest --break-system-packages && pytest ./flaskr'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker build ./flaskr -t local-flaskr'
                sh 'docker run -d --name flaskr -p 8030:8030 local-flaskr'
            }
        }
    }
}
