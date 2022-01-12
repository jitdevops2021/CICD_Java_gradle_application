pipeline{
    agent any
    options {
     buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '2', daysToKeepStr: '1', numToKeepStr: '2')
          }
    stages{
        stage("Sonar qube quality check"){
            agent {
                docker {
                    image 'openjdk:11'
                    registryUrl ''https://registry.hub.docker.com''
                }
            }
            steps{
                script{
                    withSonarQubeEnv('SonarQube-Server') {
                     sh 'chmod +x gradlew'
                     sh './gradlew sonarqube'
                    }
                }
                
            }
            
        }
    }
}    
