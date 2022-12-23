pipeline{
    agent any

    stages{
        stage('static code analysis'){
            stage{
                agent{
                    docker{
                        image: "openjdk:11"
                    }
                }
                    step{
                        withSonarQubeEnv(credentialsId: 'sonar-token') {
                            sh'chmod +x gradlew'
                            sh'./gradlew sonarqube'
                        }

                }
            }
        }
    }
}