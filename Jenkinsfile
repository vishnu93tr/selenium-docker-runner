pipeline{
    agent any
    stages{
        stage("Start grid and browsers in background mode"){
           steps{
               sh "docker-compose up -d hub chrome firefox"
           }
        }
        stage("Run Tests in chrome"){
            steps{
                sh "docker-compose up book_flight_module_chrome"
                
            }
        }
        stage("Run Tests in firefox"){
            steps{
                
                sh "docker-compose up book_flight_module_firefox"
                
            }
        }
    }
    post{
        always{
            archiveArtifacts artifacts: 'output/**'
            sh "docker-compose down"
        }
    }
}