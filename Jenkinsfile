@Library("Shared") _
pipeline{
    agent {label 'ubuntu'}
    stages{
        stage('Hello'){
            steps{
                script{
                    hello()
                }
            }
        }
        stage('Code'){
            steps{
                script{
                 clone("https://github.com/Umamahesh180396/django-notes-app.git","main")   
                }
                    
            }
        }
        stage('Build'){
            steps{
                script{
                    docker_build("latest", "mahesh545")
                }
            }
        }
        stage('Push to Docker Hub Private repo'){
            steps{
                script{
                    dockerhub_push("latest", "mahesh545")
                }
            }
        }
        stage('Deploy'){
            steps{
                script{
                    deploy()
                }
            }
        }
    }
}
