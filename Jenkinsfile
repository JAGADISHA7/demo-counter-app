pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/JAGADISHA7/demo-counter-app.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn test'
            }
        }
         stage('integtarion test') {
            steps {
                sh 'mvn verify -DskipUnitTests'
            }
        }
        stage('Maven Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('sonar qube') {
            steps {
            script {
                withSonarQubeEnv(credentialsId: 'sonarqube'){
                sh 'mvn clean package sonar:sonar'
                }
               }
            }
        }
    }
}
