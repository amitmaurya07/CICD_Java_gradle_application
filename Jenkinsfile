pipeline{
    agent any
    stages{
        stage("Sonar Check"){
            steps{
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