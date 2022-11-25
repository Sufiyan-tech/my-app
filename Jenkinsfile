def build = 1
//def currentBuildNo = currentBuild.number

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
                    switch(build){
                        case 0:
                            currentBuild.displayName = "Sufiyan Zero Build"
                            currentBuild.description = "Sufiyan Zero Description"
                            break
                        case 1:
                            currentBuild.displayName = "Sufiyan Positive Build"
                            currentBuild.description = "Sufiyan Positive Description"
                            break    
                        case -1:
                            currentBuild.displayName = "Sufiyan Negative Build"
                            currentBuild.description = "Sufiyan Negative Description"
                            break
                        default:
                            // currentBuild.displayName = "Sufiyan " + currentBuildNo + " Build"
                            // currentBuild.description = "Sufiyan " + currentBuildNo + " Description"
                            break    


                    }
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