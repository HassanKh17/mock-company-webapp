pipeline {
    agent any

    environment {
        JAVA_HOME = tool name: 'JDK 11' 
        PATH = "${JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                git branch: 'main', url: 'https://github.com/HassanKh17/mock-company-webapp.git'
            }
        }

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

    post {
        always {
            // Archive JAR files even if the build fails
            archiveArtifacts artifacts: '**/build/libs/*.jar', allowEmptyArchive: true
        }
        success {
            // If everything went well, print a success message
            echo 'Build and tests succeeded!'
        }
        failure {
            // If something went wrong, print a failure message
            echo 'Build or tests failed!'
        }
    }
}
