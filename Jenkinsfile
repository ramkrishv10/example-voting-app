pipeline{
    agent {label 'worker'}
    stages{
        stage("Build and Push"){
            steps {
                sh '''
                cd vote
                docker build -t ramkrishv10/pipeline-vote:v${BUILD_NUMBER} .
                '''
            }
        }
        stage ("Deploy"){
            steps {
                sh "docker images"
                //sh "docker login"
                //sh '''
              docker push ramkrishv10/pipeline-vote:v${BUILD_NUMBER}
              docker run -itd ramkrishv10/pipeline-vote:v${BUILD_NUMBER}
              docker ps
              '''
            }
        }
        }
        
    }
