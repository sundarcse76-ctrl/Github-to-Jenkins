pipeline {
    agent any

    tools {
        maven 'maven-3.9'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Maven Build & Test') {
            steps {
                sh 'echo "No Maven project yet; skipping mvn build"'
            }
        }
    }
}
