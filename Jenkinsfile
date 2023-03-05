pipeline{
    agent any
    stages{
        stage('Git Checkout'){
             
            step{
              git branch: 'main', credentialsId: 'raji_git', url: 'https://github.com/rajeeb007/first-maven-project.git'
            }

        }
        stage('UNIT Testing'){
             
            step{
              sh 'mvn test'
            }

        }
    }
}