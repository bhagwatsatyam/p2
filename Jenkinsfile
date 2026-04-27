pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/bhagwatsatyam/p2.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-app .'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'python test_app.py'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 5000:5000 my-app'
            }
        }
    }
}