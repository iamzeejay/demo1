pipeline {
    agent any

    tools {
        maven 'M3'
    }

    parameters {
        string defaultValue: 'adi', name: 'name', trim: true
    }

    stages {
        stage('build') {
            steps {
                bat 'mvn install -DskipTests'
            }
        }

        stage('test') {
            steps {
                bat 'echo new'
            }
            post {
                always {
                    archiveArtifacts artifacts: 'target\\**.jar', followSymlinks: false
                }
            }
        }
    }
}
