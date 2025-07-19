pipeline {
    agent any

    stages {
        stage('Start') {
            steps {
                echo 'Rozpoczynam pipeline...'
            }
        }

        stage('Checkout') {
            steps {
                git url: 'https://github.com/lukaszgolojuch/PlaywrightTests', branch: 'main'
            }
        }

        stage('Test') {
            steps {
                echo 'Uruchamiam testy'
                sh './gradlew clean test'
            }
        }

    }

}
