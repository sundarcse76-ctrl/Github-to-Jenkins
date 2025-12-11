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
                sh 'mvn -B clean test'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('sundar') {
                    sh 'mvn -B sonar:sonar'
                }
            }
        }
    }
}
