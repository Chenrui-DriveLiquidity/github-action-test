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

        stage('Build Project 1') {
            when {
                changeset "**/project_1/**"
            }
            steps {
                sh 'echo "Build Project 1"'
                sh 'cd project_1 && make hello'
            }
        }
        stage('Build Project 2') {
            when {
                changeset "**/project_2/**"
            }
            steps {
                sh 'echo "Build Project 2"'
                sh 'cd project_2 && make hello'
            }
        }
    }
}