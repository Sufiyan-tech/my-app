def build = 1


pipeline{
    agent any
    environment{
        PATH = "C:\\Windows\\System32;C:\\Users\\muhammad.sufiyan\\AppData\\Local\\Programs\\Git\\bin"
    }
    tools{
        maven 'apache-maven-3.8.6'
        jdk 'Java-JDK'
    }
    stages{
        stage('----clean----'){
            steps{
                script{
                    currentBuild.displayName = "Sufiyan Build"
                    currentBuild.description = "Sufiyan Description"
                }

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