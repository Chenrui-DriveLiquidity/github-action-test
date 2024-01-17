pipeline {
    agent { 
        docker { 
            image 'maven:3.9.6-eclipse-temurin-21-alpine' 
            args '--platform linux/arm64'
        } 
    }
    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
            }
        }
    }
}