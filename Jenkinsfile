pipeline {
    agent any

    tools {
        jdk 'JDK17'
        maven 'Maven3'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']],
                userRemoteConfigs: [[url: 'https://github.com/Praneetha2106/SE.git']]
                ])'
            }
        }

        stage('Build') {
            steps {
                echo"building the project"
                bat "mvn clean package"
            }
        }

        stage('Test') {
            steps {
                echo"testing the project"
                bat "mvn test"
            }
        }
    }
}

