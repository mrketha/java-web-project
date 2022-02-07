pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('deploy') {
            steps {
                deploy adapters: [tomcat7(credentialsId: '8dfbde01-ac7e-4990-9094-332228666982', path: '', 
                url: 'http://ec2-54-146-232-144.compute-1.amazonaws.com:8080')], contextPath: 'javawebapp', 
                war: '**/java-web-project.war'
            }
        }
    }
}
