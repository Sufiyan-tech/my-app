pipeline{
    agent any
    environment{
        PATH = "C:\\Windows\\System32"
    }
    stages{
        stage('----clean----'){
            steps{
                bat "mvn clean"
            }
        }
        stage('----test----'){
            steps{
                bat "mvn test"
            }
        }
        stage('----package----'){
            steps{
                bat "mvn package"
            }
        }
    }
}