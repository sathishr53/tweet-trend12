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
    environment {
      SCANNER_HOME = tool 'valaxy-sonar-scanner'
     }
     steps{
     withSonarQubeEnv('valaxy-sonarqube-server') {
                    sh "${scannerHome}/bin/sonar-scanner"
     }
                }
            }
        }


    }    