pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                git credentialsId: 'krishnavagu', url: 'https://github.com/krishnavagu/Boat.git'
            }
        }
        stage('Test') { 
            steps {
                sh label: '', script: 'mvn clean package'
            }
        }
        stage('Deploy') { 
            steps {
               deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://54.159.254.39:8090/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
