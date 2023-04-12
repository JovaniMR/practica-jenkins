pipeline {
    agent any

    tools { 
        nodejs "nodejs" 
    }

    stages {
        stage('checkout SCM'){
            steps {
                script{
                    git branch: 'master',
                    url: 'https://github.com/JovaniMR/practica-jenkins'
                }
            }
        }
        stage('Install dependencies'){
            steps {
                script{
                    sh 'npm install'
                }
            }
        }
        stage('Test') {
            steps {
                script{
                    sh 'ng test --no-watch --code-coverage'
                }
            }
        }
        stage('Sonar scanner coverage'){
            steps {
                script{
                    sh 'ng sonar'
                }
            }
        }
        stage('Build') {
            steps {
                script{
                    sh 'ng build --prod'
                }
            }
        }
        stage('Deploy') {
            steps {
                script{
                    echo 'Deploying'
                }
            }
        }
    }
}