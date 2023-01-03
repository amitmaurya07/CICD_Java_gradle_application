pipeline{
    agent any
    stages{
        stage("Sonar Check"){
                agent {
                    docker { 
                        image 'gradle:6.7-jdk11' 
                    }
                }
                steps {
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                        sh 'chmod +x gradlew'
                        sh './gradlew sonarqube'

                    }
            }
        }
    }
}    