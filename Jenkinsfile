pipeline{
    agent any
    stages{
        stage('Git Checkout'){
             
            steps{
              git branch: 'main', credentialsId: 'raji_git', url: 'https://github.com/rajeeb007/first-maven-project.git'
            }

        }
        stage('UNIT Testing'){
             
            steps{
              sh 'mvn test'
            }

        }
           stage('Integration testing'){
             
            steps{
              sh 'mvn verify -DskipUnitTests'
            }

        }
        stage('Maven Build'){
             
            steps{
              sh 'mvn clean install'
            }

        }
        stage('static code analysi'){
             
            steps{
                scripts{
                    withSonarQubeEnv(credentialsId: 'sonar-api') {
                    sh 'mvn clean package sonar:sonar' 
    
                 }
                }
              
            }

        }
    }
}