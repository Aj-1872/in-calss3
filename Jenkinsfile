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
                        sh 'javac src/Main.java'
                    } else {
                        bat 'javac src\\Main.java'
                    }
                }
            }
        }

        stage('Run Java Program') {
            steps {
                script {
                    echo 'Running Java program...'
                    if (isUnix()) {
                        sh 'java src.Main'
                    } else {
                        bat 'java src.Main'
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
