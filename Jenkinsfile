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
                warnError(message: 'Tests failed') {
                sh "docker-compose up --exit-code-from book_flight_module_chrome book_flight_module_firefox"
                }
            }
        }
        stage("stop grid"){
            steps{
                sh "docker-compose down"
            }
        }
    }
}