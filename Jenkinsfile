pipeline{
    agent any
    options {
     buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '1', numToKeepStr: '2')
          }
    stages{
        stage("Sonar qube quality check"){
            agent {
                docker {
                    image:'openjdk:11'
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
