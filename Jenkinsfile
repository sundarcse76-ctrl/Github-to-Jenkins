pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Hello') {
            steps {
                echo 'Hello from Jenkins'
            }
        }
    }
}
stage('Verify Maven') {
    steps {
        sh 'mvn -version'
    }
}
