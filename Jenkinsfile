pipeline {
    agent any

    tools {
        maven 'Maven3'
        jdk 'Java21'
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/shinde124dinu-Demo/maven-app.git'
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

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }

    }
}
