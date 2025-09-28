pipeline{
    agent any
    environment{
        DOCKERHUB_CREDENTIALS= "docker-hub-akki"
    }
    stages{
        stage("git_cloning"){
            steps{
                git branch: 'main', url: "https://github.com/akki9163/practise.git"
            }
        }
        stage("docker iamge building"){
            steps{
                sh "docker build -t akki9163/test:latest ."
            }
        }
        stage("docker loging"){
            steps{
                sh "echo $DOCKERHUB_CREDENTIALS_pass | docker login -u $DOCKERHUB_CREDENTIALS_usr --password-stdin"
            }
        }
        stage("docker push"){
            steps{
                sh "docker push akki9163/test:latest"
            }
        }
    }
}
