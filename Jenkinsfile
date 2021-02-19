pipeline{
    agent any
    stages{
        stage("Run Test"){
           steps{
               sh "docker-compose up"
           }
        }
        stage("bring grid down"){
            steps{
                sh "docker-compose down"
            }
        }
    }
}