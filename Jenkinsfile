node {
    checkout scm

    try {
        stage('Test') {
            sh './gradlew test --stacktrace --debug'
        }
    } finally {
        archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
        junit 'build/reports/**/*.xml'
    }
}