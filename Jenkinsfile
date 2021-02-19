pipeline{
    agent any
    stages{
        stage("Run Test"){
           step{
               sh "docker-compose up"
           }
        }
        stage("bring grid down"){
            step{
                sh "docker-compose down"
            }
        }
    }
}