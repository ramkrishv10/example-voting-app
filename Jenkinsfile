pipeline{
    agent any
    stages{
        stage("Build and Push"){
            steps {
                sh '''
                cd vote
                docker build -t ramkrishv10/pipeline-vote:v1 .
                '''
            }
        }
        stage ("Deploy"){
            steps {
                sh "docker images"
                sh "docker login"
                sh '''
              docker push ramkrishv10/pipeline-vote:v1
              docker run -itd ramkrishv10/pipeline-vote:v1
              docker ps
              '''
            }
        }
        }
        
    }
