pipeline {
    agent any

    stages {

        // stage('Clone Repository') {
        //     steps {
        //         git 'https://github.com/Nikhil-SY/Java_app.git'
        //     }
        // }

        stage('Build Maven Project') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t calculator-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d --name calculator-container calculator-app'
            }
        }

    }
}
