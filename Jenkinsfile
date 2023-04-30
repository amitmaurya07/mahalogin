pipeline{
    agent any
    stages{
        stage("Checkout"){
            steps{
                git 'https://github.com/amitmaurya07/mahalogin.git'
            }
            }      
        stage("Maven Build"){
            steps{
                sh 'mvn clean install'            
                }
        }        
        stage("Sonar Check"){
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonarqube_token') {
                        sh "mvn clean package sonar:sonar"
                    }
                }
            }
    }   }
}
