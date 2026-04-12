pipeline {
    agent {
        node {
            label 'maven'
        }
    }
    environment {
        PATH = "/opt/apache-maven-3.9.6/bin:$PATH"
    }
    stages {
        stage("Build") {
            steps {
                sh 'mvn clean deploy -Dmaven.test.skip=true -e'
           }
        }
    
stage('SonarQube Analysis') {
    steps {
        withSonarQubeEnv('SonarQube-Server') {
            sh '''
            sonar-scanner \
              -Dsonar.projectKey=tweet-trend12 \
              -Dsonar.projectName=tweet-trend12 \
              -Dsonar.sources=. \
              -Dsonar.host.url=https://sonarcloud.io \
              -Dsonar.login=$SONAR_TOKEN
            '''
        }
    }
}
    }
}