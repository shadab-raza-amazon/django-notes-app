@Library("Shared") _
pipeline{
    agent{ label "agent"}
    
    stages{
        
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        
        stage("code"){
            steps{
                script{
                clone("https://github.com/shadab-raza-amazon/django-notes-app.git","dev")
                }
               
            }
    }
        stage("build"){
            steps{
              script{  
              build("notes-app","latest","shadab00786")
              }
            }
        }
        stage("Push to Docker Hub"){
            steps{
               script{
                   push("notes-app","latest","shadab00786")
                }
            }
        }
        stage("Deploy"){
            steps{
                echo "this is deploying the code"
                sh "docker compose up -d"
            }
        }
    }
    }
