node {
    checkout scm

    try {
        stage('Build') {
            sh './gradlew bootJar'
        }
        stage('Test') {
            sh './gradlew test'
        }
    } finally {
        archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
        junit 'build/test-results/**/*.xml'
    }
}