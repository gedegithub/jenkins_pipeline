pipeline {
    agent any
    environment {
        JAVA_HOME = '/usr/lib/jvm/java-17-openjdk-amd64/'
        PYTHON_HOME = '/usr/bin/python3' //'C:\\Users\\rehou\\AppData\\Local\\Programs\\Python\\Python39'
        PATH = "${env.PATH}:${JAVA_HOME}/bin:/usr/bin" //'${env.PATH};${JAVA_HOME}\\bin;${PYTHON_HOME}'
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
                            sh 'javac HelloWorld.java'
                            sh 'java HelloWorld'
                            sh 'python3 hello.py'
                        
                    } else {
                            bat 'echo "Running on Windows"'
                            bat 'echo "Set environment variables for windows"'
                            bat 'javac HelloWorld.java'
                            bat 'java HelloWorld'
                            bat 'python hello.py'
                    }
                }
            }
        }
    }
}
