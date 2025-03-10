pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Aj-1872/in-calss3.git'
            }
        }
        stage('Build Java Project') {
            steps {
                sh 'javac Main.java'
            }
        }
        stage('Run Java Program') {
            steps {
                sh 'java Main'
            }
        }
    }
}
