pipeline {
    agent any

    environment {
        JAVA_HOME = tool name: 'JDK 11' 
        PATH = "${JAVA_HOME}/bin:${env.PATH}"
    }

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
