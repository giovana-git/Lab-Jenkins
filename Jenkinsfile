pipeline {
    agent any

    stages {

        stage('Inicial') {
            steps {
                echo 'Iniciando a pipeline'
            }
        }


        stage('Origem do GitHub') {
            steps {
                git url: 'https://github.com/giovana-git/Lab-Jenkins.git', branch: 'main'
            }
        }

        stage('Build das imagens Docker') {
            steps {
                script {
                    dockerappa = docker.build("giovanacosta/app-a:${env.BUILD_ID}", '-f pipeline-jenkins/Lab-Jenkins/app-a .')
                    dockerappb = docker.build("giovanacosta/app-b:${env.BUILD_ID}", '-f pipeline-jenkins/Lab-Jenkins/app-b .')
                    dockerappc = docker.build("giovanacosta/app-c:${env.BUILD_ID}", '-f pipeline-jenkins/Lab-Jenkins/app-c .')
                    dockerappd = docker.build("giovanacosta/app-d:${env.BUILD_ID}", '-f pipeline-jenkins/Lab-Jenkins/app-d .')
                }
            }
        }

        stage('Push imagem para o DockerHub') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com/', 'dockerhub') {
                        dockerappa.push("${env.BUILD_ID}")
                        dockerappb.push("${env.BUILD_ID}")
                        dockerappc.push("${env.BUILD_ID}")
                        dockerappd.push("${env.BUILD_ID}")
                    }
                }
            }
        }
        // stage('Deploying App to Kubernetes') {
        //     steps {
        //         script {
        //             kubernetesDeploy(configs: "deploymentservice.yml", kubeconfigId: "kubernetes"                    
        //         }
        //     }
        // }
    }
}