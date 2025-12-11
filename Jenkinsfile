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
                withSonarQubeEnv('sundar') {   // or your server name
                    sh 'mvn -B sonar:sonar'
                }
            }
        }

        stage('Quality Gate') {
            steps {
                script {
                    timeout(time: 5, unit: 'MINUTES') {
                        def qg = waitForQualityGate()
                        if (qg.status != 'OK') {
                            error "Pipeline failed due to Quality Gate status: ${qg.status}"
                        }
                    }
                }
            }
        }
    }
}
