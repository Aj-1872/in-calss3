pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    echo 'Cloning repository...'
                }
            }
        }

        stage('Compile Java Code') {
            steps {
                script {
                    echo 'Compiling Java code...'
                    if (isUnix()) {
                        sh 'javac Main.java'
                    } else {
                        bat 'javac Main.java'
                    }
                }
            }
        }

        stage('Run Java Program') {
            steps {
                script {
                    echo 'Running Java program...'
                    if (isUnix()) {
                        sh 'java Main'
                    } else {
                        bat 'java Main'
                    }
                }
            }
        }
    }

    post {
        always {
            echo 'Cleaning up workspace...'
            deleteDir()
        }
    }
}
