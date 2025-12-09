pipeline {
    agent any

    tools {
        maven 'maven-3.9'   // same name as in Global Tool Configuration
    }

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
        stage('Verify Maven') {
            steps {
                sh 'mvn -version'
            }
        }
    }
}
