pipeline{
    agent any
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
    post{
        always{
            echo "Hi Build is sucess"
        }
        
    }
}
