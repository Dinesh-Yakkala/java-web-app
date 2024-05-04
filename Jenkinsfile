pipeline {
    agent any
    
    stages {
        stage('checkout code') {
            steps {
                git branch: 'main', url: 'https://github.com/Dinesh-Yakkala/java-web-app.git'
            }
        }
        stage('build code') {
            steps {
                sh '/opt/maven/bin/mvn clean package'
            }
        }
        stage('Deployment'){
			steps{
				deploy adapters: [ tomcat9(url: 'http://18.209.20.254:8080/', credentialsId: 'tomcat-cred')], war:'target/*.war'
			}
		}
    }
}
