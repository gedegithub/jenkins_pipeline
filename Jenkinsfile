pipeline {
    agent any
    environment {
        PATH = "${env.PATH}:/usr/bin/python3"
    }
    stages {
        stage('Checkout') {
            steps {
               git branch: 'main', url: 'https://github.com/gedegithub/jenkins_pipeline.git'
            }
        }
        stage('Build') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'echo "Running on Unix"'
                        // Add your Unix-specific build commands here
                        sh 'javac HelloWorld.java'
                        sh 'java HelloWorld'
                        sh 'python3 hello.py'
                    } else {
                        bat 'echo "Running on Windows"'
                        // Add your Windows-specific build commands here
                        bat 'javac HelloWorld.java'
                        bat 'java HelloWorld'
                        bat 'python3 hello.py'
                    }
                }
            }
        }
    }
}
