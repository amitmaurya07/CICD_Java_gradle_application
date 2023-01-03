pipeline{
    agent any
    stages{
        stage("Sonar Check"){
                agent {
                    docker { 
                        image 'openjdk:11-jre-slim' 
                        reuseNode true
                    }
                }
                steps {
                    script{
                     withSonarQubeEnv(credentialsId: 'sonar-token') {
                        sh 'sudo chmod +x gradlew'
                        sh './gradlew sonarqube'
                    }

                }
            }
        }
    }
}    