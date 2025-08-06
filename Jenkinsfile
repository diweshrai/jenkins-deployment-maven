pipeline {
    agent any

    triggers {
        pollSCM('* * * * *') // For test only. Use webhook in real use.
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/YOUR_USERNAME/YOUR_REPO.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Run Jar') {
            steps {
                sh 'java -jar target/demo-1.0-SNAPSHOT.jar'
            }
        }
    }
}
