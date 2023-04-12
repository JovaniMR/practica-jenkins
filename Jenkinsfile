pipeline {
    agent any

    tools { 
        nodejs "NodeJS" 
    }

    stages {
        stage('checkout SCM'){
          git branch: 'master',
          url: 'https://github.com/JovaniMR/practica-jenkins'
        }
        stage('Install dependencies'){
            sh: 'npm install'
        }
        stage('Test') {
            sh: 'ng test --no-watch --code-coverage'
        }
        stage('Sonar scanner coverage'){
            sh: 'ng sonar'
        }
        stage('Build') {
            sh: 'ng build --prod'
        }
        stage('Deploy') {
            echo 'Deploying'
        }
    }
}