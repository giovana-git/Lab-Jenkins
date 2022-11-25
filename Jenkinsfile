pipeline {
    agent any

    stages {
        stage('Inicial') {
            steps {
                echo 'Iniciando a pipeline'
            }
        }

    stages {
        stage('Origem do GitHub') {
            steps {
                git url: 'https://github.com/giovana-git/Lab-Jenkins.git', branch: 'main'
            }
        }
    }

    stages {
        stage('Build das imagens Docker') {
            steps {
                dockerappa = docker.build("giovanacosta/app-a:latest"
                dockerappb = docker.build("giovanacosta/app-b:latest"
                dockerappc = docker.build("giovanacosta/app-c:latest"
                dockerappd = docker.build("giovanacosta/app-d:latest"
                
            }
        }
    }

    stages {
        stage('Push imagem para o DockerHub') {
            steps {
                docker.withRegistry('https://registry.hub.docker.com/', 'dockerhub')
                dockerappa.push('latest')
                dockerappb.push('latest')
                dockerappc.push('latest')
                dockerappd.push('latest')

            }
        }
    }
    }
}