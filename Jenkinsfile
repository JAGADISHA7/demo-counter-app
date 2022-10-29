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
    }
}
