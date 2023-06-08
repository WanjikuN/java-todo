pipeline{
    agent any
 
    tools {
        gradle 'Gradle-6'
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
        // stage('Deploy to Heroku'){
        //     steps {
        //         withCredentials([usernameColonPassword(credentialsId: 'heroku', variable: 'HEROKU_CREDENTIALS')]) {
        //             sh 'git push https://${HEROKU_CREDENTIALS}@git.heroku.com/java-todo3.git master'
            
          
        //         }
        //     }
        // }
        // stage('Slack notification'){
        //     steps{
        //        slackSend channel: '#random', color: '#008000', message: "successfully deployed ${env.JOB_NAME} ${env.BUILD_NUMBER} to (<https://java-todo3.herokuapp.com/|Java-todo3>) ", teamDomain: 'wanjiku-workspace', tokenCredentialId: 'slack2', username: 'pat_Jenkins'
                
        //     }
        // }
        
        
    }

}
