pipeline {
    agent { 
        docker { 
            image 'maven:3.9.6-eclipse-temurin-21-alpine' 
            args '--platform linux/arm64 -u root'
        } 
    }
    stages {
        stage('build') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
                sh 'mvn --version'
                sh 'apk add --no-cache make'
                sh 'make hello'
            }
        }
    }
}