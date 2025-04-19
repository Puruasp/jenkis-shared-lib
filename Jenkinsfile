@Library("shared") _
pipeline{
    agent { label "vinod"}
    
    stages{
        stage("Hello"){
            steps{
                
                    hello()
                            }
        }
         stage("Code"){
                steps{
                                        clone("https://github.com/Puruasp/django-notes-app.git", "main")
                
            }
         }
            stage("Build"){
                steps{
                    
                        docker_build("note-app", "latest","unomeakki")
                    
                                 }
            }
            stage('Push to DockerHub'){
                steps{
                   
                       docker_push("notes-app", "latest", "unomeakki")
                          
                       }
                                      }
            stage("Deploy"){
                steps{
                    echo "this is Deploying  the code"
                    sh "docker compose up -d"
                                    }
            }
    }
    
}
