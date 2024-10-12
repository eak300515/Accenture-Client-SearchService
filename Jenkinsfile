pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // TODO: Add build command here
                sh './gradlew assemble'
            }
        }
        stage('Test') {
            steps {
                // TODO: Add test command here
                sh './gradlew test'
            }
        }
    }
    post {
        always {
            junit 'build/test-results/**/*.xml'
            archiveArtifacts artifacts: 'build/libs/**/*.jar', allowEmptyArchive: true
        }
        failure {
            echo 'The build has failed.'
        }
    }
}
