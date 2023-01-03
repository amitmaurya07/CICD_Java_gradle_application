pipeline{
    agent any
    stages{
        stage("Sonar Check"){
            steps{
                agent {
                    docker { 
                        image 'gradle:6.7-jdk11' }
                }
                script {
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                        sh 'chmod +x gradlew'
                        sh './gradlew sonarqube'

                    }
                }
            }
        }
    }
}