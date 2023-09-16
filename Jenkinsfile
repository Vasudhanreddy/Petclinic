pipeline {
    agent any
    tools{
        jdk 'jdk11'
        maven 'maven3'
    }
    stages {
        stage('git checkout') {
            steps {
               git branch: 'main', url: 'https://github.com/Vasudhanreddy/Petclinic.git' 
            }
        }
        stage('compile') {
            steps {
               sh "mvn clean compile"
            }
        }
        stage('build') {
            steps {
               sh "mvn clean package -DskipTests=true"
            }
        }
        stage('deploy') {
            steps {
                sh "cp target/petclinic.war /opt/apache-tomcat-9.0.65/webapps "
            }
        }
    }
}

