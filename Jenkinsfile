pipeline {
    agent none  // Avoid using a global agent at the pipeline level
    stages {
        stage('Build') {
            agent { docker 'maven:3.9.3-eclipse-temurin-17' }
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            agent { docker 'openjdk:17-jdk' }
            steps {
                sh 'java -jar target/my-app-tests.jar'
            }
        }
    }
}