pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'mvn clean install'
                
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                deploy adapters: [tomcat7(credentialsId: 'c28fa98d-668e-4a2f-bde6-82b6351a8a9e', path: '', url: 'http://localhost:8090/')], contextPath: '/cinema/movies', war: '**/*.war'
            }
        }
    }
}

