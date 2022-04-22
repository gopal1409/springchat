pipeline {
    agent any
    tools {
        maven "localMaven"
    }
    stages {
        stage('checkout scm') {
            steps {
                git credentialsId: 'github-token', url: 'https://github.com/gopal1409/springchat.git'
            }
        } 
        stage('ansible prov'){
            steps {
               
            }
        }
    }
}
