pipeline{
    agent any
 
    tools {
        gradle 'Gradle-8'
    }
    stages{
        stage('Clone Repository' ){
            steps{
                git 'https://github.com/WanjikuN/java-todo.git'
            }
        }
        stage('Build'){
            steps{
                sh 'gradle build'
            }
        }
        stage('Email notification'){
            steps{
                mail bcc: '', body: 'This is our group test', cc: '', from: '', replyTo: '', subject: 'Jenkins pipeline test', to: 'patricia.njoroge@student.moringaschool.com, cikunjoroge4@gmail.com'
            }
        }
        stage('Test'){
            steps{
                sh 'gradle test'
            }
        }
        stage('Deploy to Heroku'){
            steps{
               withCredentials([usernameColonPassword(credentialsId: 'Heroku1', variable: 'PASS')]) {
                    sh 'git push https://${PASS}@git.heroku.com/java-todo1.git master' } 
            }
        }
        stage('Slack Notifications'){
            steps{
                slackSend channel: '#trial', color: 'green', message: "successful deployment of ${env.JOB_NAME}", teamDomain: 'wanjiku-workspace', tokenCredentialId: 'slack2' 
                 }
        }
        
        
    }

}
