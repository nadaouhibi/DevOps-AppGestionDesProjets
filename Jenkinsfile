pipeline {
    agent any

    stages {

        stage('Backend - Spring Boot') {
            steps {
                dir('backend') {
                    sh 'mvn clean package -DskipTests'
                }
            }
        }

        stage('Frontend - Angular') {
            steps {
                dir('frontend') {
                    sh 'npm install'
                    sh 'npm run build'
                }
            }
        }
    }

    post {
        success {
            echo 'Backend et Frontend compilés avec succès !'
        }
        failure {
            echo 'Erreur lors de la compilation.'
        }
    }
}
