pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                // Run the Gradle build
                sh './gradlew assemble'
            }
        }

        stage('Test') {
            steps {
                // Run the Gradle tests
                sh './gradlew test'
            }
        }
    }
}
