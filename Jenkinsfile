pipeline {
    agent any

    tools {
        maven 'Jenkins-Maven'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Maven Build & Test') {
            steps {
                sh 'mvn -B clean test'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('sonarqube-local') {
                    sh 'mvn -B clean verify sonar:sonar'
                }
            }
        }
    }
}
