pipeline {
    agent any 
    stages {
        stage ('Git-Commit')
         {
 git credentialsId: 'krishnavagu', url: 'https://github.com/krishnavagu/Boat.git'
}
 stage ('maven-project')
{
sh label: '', script: 'mvn clean package'
}
stage ('Deployment')
{
deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://54.159.254.39:8090/')], contextPath: null, war: '**/*.war'
}
    }
}
