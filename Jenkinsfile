int build = 5

class BuildSettings{
    static String name;
    static String description;
    static int currentBuildNo;

    // public BuildSettings(int currentBuildNo){
    //     currentBuildNo = currentBuildNo;
    // }

    static void getDetails(int build){
        switch(build){
            case 0:
                name = "Sufiyan Zero Build"
                description = "Sufiyan Zero Description"
                break 
            case {build > 0}:
                name = "Sufiyan Positive Build"
                description = "Sufiyan Positive Description"
                break
            case {build < 0}:
                name = "Sufiyan Negative Build"
                description = "Sufiyan Negative Description"
                break   
            default:
                name = "Sufiyan " + currentBuildNo + " Build"
                description = "Sufiyan " + currentBuildNo + " Description"
                break     
        }        
    }
}


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
                    BuildSettings.getDetails(5);
                    // currentBuild.displayName = bs.name
                    // currentBuild.description = bs.description
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