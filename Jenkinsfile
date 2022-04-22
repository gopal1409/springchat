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
        stage('mvn build'){
            steps {
                sh "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }
        stage('mvn test'){
            steps {
                sh "mvn test"
            }
        }
        stage('test report'){
            steps {
                junit 'target/surefire-reports/*.xml'
            }
        }
        stage('check style'){
            steps {
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('check style view'){
            steps {
                recordIssues(tools: [checkStyle(pattern: 'target/checkstyle-result.xml')])
            }
        }
    }
}
