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
node {
    stage('Checkout') {
        checkout scm
    }

    stage('Hello') {
        echo 'Hello from Jenkins'
    }

    stage('Verify Maven') {
        sh 'mvn -version'
    }
}

