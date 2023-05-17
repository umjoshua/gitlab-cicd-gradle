pipeline{
    agent any
    stages{
        stage("Sonar Quality Test"){
            agent {
                docker {
                    image "openjdk:11"
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-jenkins-id') {
                        sh 'chmod +x gradlew'
                        sh './gradlew sonarqube'
                    }
                }
            }
            post{
                always{
                    echo "========always========"
                }
            }
        }
    }
}