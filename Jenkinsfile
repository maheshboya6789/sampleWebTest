pipleline{
    agent any
    stages{
        stage('Git SCM'){
            git 'https://github.com/maheshboya6789/sampleWebTest.git'
        }
        stage('Sonar Quality Check'){
            agent {
                docker {
                    image 'openjdk:11'
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                            sh 'chmod +x gradlew'
                            sh './gradlew sonarqube'
                        }

                    }
            }
           
        }
    }
   
}