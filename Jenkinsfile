pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('Code Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Acharya-sh/SEPM-EXP-05.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                bat 'copy target\\*.war C:\apache-tomcat-9.0.117\webapps'
            }
        }
    }
}