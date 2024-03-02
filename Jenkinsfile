pipeline{
    agent any
    environment{
        name1="java"
        name2="Jenkins"
    }
    stages{
        stage("Concatination"){
            steps{
                script{
                    Name = name1 +"with" +name2
                }
                echo "Welcome to $Name"
            }
        }
    }
}