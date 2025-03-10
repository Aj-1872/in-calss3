pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    // This step will automatically be handled by Jenkins SCM, no need to clone manually
                    echo 'Cloning repository...'
                }
            }
        }

        stage('Compile Java Code') {
            steps {
                script {
                    echo 'Compiling Java code...'
                    if (isUnix()) {
                        // Unix-based system (Linux, macOS)
                        sh 'javac Main.java'
                    } else {
                        // Windows system
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
                        // Unix-based system (Linux, macOS)
                        sh 'java Main'
                    } else {
                        // Windows system
                        bat 'java Main'
                    }
                }
            }
        }
    }

    post {
        always {
            echo 'Cleaning up workspace...'
            deleteDir()  // Clean up the workspace after build completes
        }
    }
}
