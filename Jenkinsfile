pipeline {
    agent any
    stages {
        stage ('Build') {
            steps {
                sh 'mvn clean package'        
            }
        }
        stage ('Deploy') {
             steps {
                deploy adapters: [tomcat8(credentialsId: 'login-tomcat', path: '', url: 'http://172.17.0.1:8001/')], contextPath: 'tasks-backend', war: 'target/tasks-backend.war'
             }
        }
    }
}