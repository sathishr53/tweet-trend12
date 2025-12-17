pipeline {
    agent {
        node {
            label 'maven'
        }
    }
environment {
        PATH = "/opt/apache-maven-3.9.6/bin:$PATH"
    }
     stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
}

