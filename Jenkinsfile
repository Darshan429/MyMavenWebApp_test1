pipeline {
    agent any  

    tools {
        maven 'MAVEN'  
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Darshan429/MyMavenWebApp_test1.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test' 
            }
        }
        stage('Deploy WAR') {
            steps {
                sh 'cp target/MyMavenWebApp_test1.war /opt/tomcat/webapps/'
            }
        }   
    }
    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
