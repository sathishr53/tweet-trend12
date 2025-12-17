 

pipeline {
    agent any
    tools {
        maven // 'M3' should match the name configured in Global Tool Configuration
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}