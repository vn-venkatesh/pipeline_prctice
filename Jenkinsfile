pipeline{
    agent any
    environment {
        DOCKER_TAG = getDockerTag{}
    }

    stages{
        stage("build docker image"){
            steps{
                sh "docker build . -t venkatesh/nodeapp:${DOCKER_TAG}"
            }
        }
    }
}

def getDockerTag(){
    def tag = sh script: "git rev-parse HEAD", returnStdout: true
    return tag
}