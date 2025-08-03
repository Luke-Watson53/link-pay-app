pipeline {
    agent any
tools {
  maven 'MVN_3.9.11'
}
    stages {
        stage('Git checkout') {
            steps {
                git branch: 'main', credentialsId: 'GitHHub_SCM', url: 'https://github.com/Luke-Watson53/link-pay-app.git'
            }
        }
        stage('Maven_build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Quality_test') {
            steps {
                sh 'mvn sonar:sonar'
            }
        }
    }
}