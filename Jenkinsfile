pipeline{
    agent any
    stages{
        stage("welcome"){
            steps{
                echo "welcome to my pipeline, Exicution started"
            }
        }
        stage("building docker image"){
            steps{
                sh "docker pull alpine"
            }
        }
        stage("running docker image"){
            steps{
                sh "docker run -itd alpine /bin/bash/"
            }
        }
    }
}
