CurrentBuild.displayNamee = "my_first_pipeline_#"+CurrentBuild.number
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

        stage(push image to docker hub){
            steps{
                withCredentials([string(credentialsId: 'dockehub_password', variable: 'dockerhub_pwd')]) {
                    sh "docker login -u vnagavenkatesh503@gmail.com -p ${dockerhub_pwd}"
                    sh "docker push venkatesh/nodeapp:${DOCKER_TAG}"
                }
                
            }
        }
    }
}

def getDockerTag(){
    def tag = sh script: "git rev-parse HEAD", returnStdout: true
    return tag
}