pipeline {
    agent any

    tools {
        maven 'Maven3'
        jdk 'JDK11'
    }
environment {
        PATH = "/opt/apache-maven-3.9.11/bin:$PATH"
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}

