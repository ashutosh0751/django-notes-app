@Library("shared") _

pipeline {
    agent { label "vinod"}
    
    stages {
        stage("hello") {
            steps {
                hello()
            }
        }
        stage("code") {
            steps{
                echo "this is cloning the code"
                git url: "https://github.com/ashutosh0751/django-notes-app.git", branch: "main"
                echo "cloning the code SUCCESS"
            }
        }
        stage("build") {
            steps{
                 echo "this is building the code"
                 sh "whoami"
                 sh "docker build -t notes-app:latest ."
            }
        }
        stage("test") {
            steps{
                 echo "this is testing the code"
            }
        }
        stage("deploy") {
            steps{
                 echo "this is deploying the code"
                 sh "docker compose up -d"
            }
        }
    }
}
