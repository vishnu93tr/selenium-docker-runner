pipeline{
    agent any
    stages{
        stage("Start grid and browsers in background mode"){
           steps{
               sh "docker-compose up -d hub chrome firefox"
           }
        }
        stage("Run Tests"){
            steps{
                sh "docker-compose up  book_flight_module_chrome book_flight_module_firefox"
            }
        }
        stage("stop grid"){
            steps{
                sh "docker-compose down"
            }
        }
    }
}