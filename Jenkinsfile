@Library("Shared") _
pipeline{
    agent { label "agent1" }
    
    stages{
        
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("Code"){
            steps{
                script{
                    clone("https://github.com/mohit4848/django-notes-app.git","main")
                }
            }
        }
        stage("Build"){
            steps{
                script{
                    docker_build("notes-app","latest","mohit4848")
                }
            }
        }
        stage("Push to DockerHub"){
            steps{
                script{
                    docker_push("notes-app", "latest", "mohit4488")
                }
            }
        }
        stage("Deploy"){
            steps{
                echo "This is deploying the code"
                sh "docker compose up -d"
            }
        }
    }
}
