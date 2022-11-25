int build = 5

class BuildSettings{
    def name;
    def description;
    int currentBuildNo;

    // public BuildSettings(int currentBuildNo){
    //     this.currentBuildNo = currentBuildNo;
    // }

    public void getDetails(int build){
        switch(build){
            case 0:
                this.name = "Sufiyan Zero Build"
                this.description = "Sufiyan Zero Description"
                break 
            case {build > 0}:
                this.name = "Sufiyan Positive Build"
                this.description = "Sufiyan Positive Description"
                break
            case {build < 0}:
                this.name = "Sufiyan Negative Build"
                this.description = "Sufiyan Negative Description"
                break   
            default:
                this.name = "Sufiyan " + this.currentBuildNo + " Build"
                this.description = "Sufiyan " + this.currentBuildNo + " Description"
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
                    BuildSettings bs = new BuildSettings();
                    bs.getDetails(5);
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