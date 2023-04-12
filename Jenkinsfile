pipeline {
    agent any

    tools { 
        nodejs "NodeJS" 
    }
    
    stages {
        stage('Install dependencies'){
            steps {
                sh: 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh: 'ng test --no-watch --code-coverage'
            }
        }
        stage('Sonar scanner coverage'){
            steps {
                sh: 'ng sonar'
            }
        }
        stage('Build') {
            steps {
                sh: 'ng build --prod'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
            }
        }
    }
}