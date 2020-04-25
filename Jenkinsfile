pipeline {
    agent any
    stages {
        stage('Build Jar') {
            steps {
                    bat 'mvn clean package -DskipTests'
            }
        }
        stage('Build Image') {
            steps {
                    bat "docker build -t=sagarmopagar/selenium-docker:1.0 ."
            }
        }
        stage('Push Image') {
            steps {
            //    withCredentials([usernamePassword(credentialsId:'dockerhub', passwordVariable:'pass', usernameVariable:'user')])
                bat "docker push sagarmopagar/selenium-docker:1.0"
            }
        }
    }
}