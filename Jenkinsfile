node {
    try {
        stage('Test') {
            sh './gradlew check'
        }
    } finally {
        archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
        junit 'build/reports/**/*.xml'
    }
}