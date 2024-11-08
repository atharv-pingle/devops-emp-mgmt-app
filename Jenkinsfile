pipeline {
    agent any
    stages {
        stage('Clone Repo') {
            steps {
                git '<https://github.com/atharv-pingle/devops-emp-mgmt-app.git>'
            }
        }
        stage('Build Backend') {
            steps {
                script {
                    sh 'docker build -t asp0217/go-backend .'
                }
            }
        }
        stage('Push Backend Image') {
            steps {
                script {
                    sh 'docker push asp0217/go-backend'
                }
            }
        }
        stage('Build Frontend') {
            steps {
                script {
                    sh 'docker build -t asp0217/react-frontend .'
                }
            }
        }
        stage('Push Frontend Image') {
            steps {
                script {
                    sh 'docker push asp0217/react-frontend'
                }
            }
        }
        stage('Deploy with ArgoCD') {
            steps {
                script {
                    sh 'kubectl argo sync emp-app'
                }
            }
        }
    }
}
