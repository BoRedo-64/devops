pipeline {
    agent any

    tools {
        jdk 'JAVA_HOME'
        maven 'M2_HOME'
    }

    stages {

        stage('GIT') {
            steps {
                git branch: 'main',
                url: 'https://github.com/BoRedo-64/devops.git'
            }
        }

        stage('Compile Stage') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t boredo64/devops-app:1.0 .'
            }
        }

    }
}
