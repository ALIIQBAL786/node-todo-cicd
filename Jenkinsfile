@Library("Hello") _
pipeline {
    agent { label 'vinod' }
    
    stages {
        stage("Hello") {
            steps {
                script {
                    hello()
                }
            }
        }
        stage("Code") {
            steps {
                script {
                    clone("https://github.com/ALIIQBAL786/node-todo-cicd.git", "main")
                }
            }
        }
        stage("Build") {
            steps {
                script {
                    build("notes-app", "latest", "aliiqbal003")
                }
            }
        }
        stage("Push to DockerHub") {
            steps {
                script {
                    docker_push("notes-app", "latest", "aliiqbal003")
                }
            }
        }
        stage("Deploy") {
            steps {
                script {
                    deploy()
                }
            }
        }
    }
}
