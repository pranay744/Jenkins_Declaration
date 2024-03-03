pipeline{
    agent any
    parameters{
        choice(name:'GIT',choice:['Dev','Stage','Prod'],description:'Please Enter your Git repo here:')
    }
    stages{
        stage("Executing Git repo"){
            steps{
                script{
                    echo 'Exeruing GiT Repo.....'
                    if(params.GIT=="Dev"){
                        echo "Executing Dev Repo..."
                        git branch: 'development', credentialsId: '94ec7097-5be2-4b2b-b5e7-e54f4f085314', url: 'https://github.com/MithunTechnologiesDevOps/maven-web-application.git'
                    }
                    else if([params.GIT=="Stage"]){
                        echo 'Executing Stage Repo...'
                        git branch: 'stage', credentialsId: '94ec7097-5be2-4b2b-b5e7-e54f4f085314', url: 'https://github.com/MithunTechnologiesDevOps/maven-web-application.git'
                    }
                    else{
                        echo "Executing Dev Repo..."
                        git credentialsId: '94ec7097-5be2-4b2b-b5e7-e54f4f085314', url: 'https://github.com/MithunTechnologiesDevOps/maven-web-application.git'
                    }
                }
            }
        }
        stage("Executing Maven Build"){
            steps{
                script{
                    sh 'mvn clean package'
                }
            }
        }
        stage("Executing Sonar report"){
            steps{
                sh 'mvn clean package sonar:sonar'
            }
        }
        stage("Upload into Nexus Repo"){
            steps{
                echo "Uploding into Rep...."
            }

        }
        stage("Deploy into continer"){
            steps{
                echo "Deploying into Continer"
            }
        }
    }
}