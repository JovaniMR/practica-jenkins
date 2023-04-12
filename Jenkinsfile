pipeline {
    agent any

    tools { 
        nodejs "node" 
    }

    stages {
        stage('checkout SCM'){
            steps {
                git branch: 'master',
                url: 'https://github.com/JovaniMR/practica-jenkins'
            }
        }
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
                //sh: 'ng build --prod'
                echo 'buildying'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
            }
        }
    }
}