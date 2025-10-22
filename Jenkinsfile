@Library("Shared") _

pipeline {
    agent { label "pujan" }

    stages {
        stage('Clone') {
            steps {
                echo 'This is cloning'
                script {
                    clone("https://github.com/PujanPraz/hello-website.git/", "main")
                }
            }
        }
        stage('Build') {
            steps {
                echo 'This is building the code'
                script {
                    build("pujanprajapati", "hello-website", "latest")
                }
            }
        }
        stage('push') {
            steps {
                echo 'This is pushing the code'
                script{
                    push("hello-website", "latest")
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'This is deploying the code'
                sh "docker compose down && docker compose up -d"
            }
        }
    }
}

