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
                sh "docker run -itd alpine"
            }
        }
        stage("push umage to dockerhub"){
            steps{
                withCredentials([string(credentialsId: 'dockehub_password', variable: 'dockerhub_pwd')]) {
                    sh "docker login -u vnagavenkatesh503@gmail.com ip ${dockerhub_pwd}"
                    sh "docker push alpine"
                }
            }
        }
    }
}
