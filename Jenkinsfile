pipeline{
    agent any
    stages{
        stage("Start grid and browsers in background mode"){
           steps{
               sh "docker-compose up -d hub chrome firefox"
           }
        }
        stage("Run Tests and check for failures"){
            steps{
                warnError(message: book_flight_module_chrome is failed){
                    sh "docker-compose up --exit-code-from book_flight_module_chrome"
                }
                warnError(message: book_flight_module_firefox is failed){
                    sh "docker-compose up --exit-code-from book_flight_module_firefox"
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