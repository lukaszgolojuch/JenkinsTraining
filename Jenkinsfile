pipeline {
    agent any

    parameters {
        string(name: 'BRANCH', defaultValue: 'main', description: 'Branch do checkoutu')
        booleanParam(name: 'RUN_TESTS', defaultValue: 'true', description: 'Czy uruchomić testy?')
    }

    stages {
        stage('Start') {
            steps {
                echo 'Rozpoczynam pipeline...'
            }
        }

        stage('Checkout') {
            steps {
                git url: 'https://github.com/lukaszgolojuch/PlaywrightTests', branch: "$params.BRANCH"
            }
        }

        stage('Test') {
            when {
                expression { return params.RUN_TESTS == true }
            }
            steps {
                echo 'Uruchamiam testy'
                sh './gradlew clean test'
            }
        }

    }

}
