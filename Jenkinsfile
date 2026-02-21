pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Build') {
            when {
                branch 'main'
            }
            steps {
                sh 'dotnet build'
            }
        }
        
        stage('Test') {
            when {
                branch 'main'
            }
            steps {
                sh 'dotnet test'
            }
        }
    }
}