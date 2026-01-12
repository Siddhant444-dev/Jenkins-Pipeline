pipeline {
    agent any
    tools {
        maven "jenkins-maven"
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/jenkins-docs/simple-java-maven-app.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') { 
            steps {
                sh 'mvn test' 
            }
            post{
                always{
                    junit '**/target/surefire-reports/TEST-*.xml'
                }
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo Deployed'
            }
        }
    }
}
