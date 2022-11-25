pipeline {
    agent any

    // environment {
    //     registry = "giovanacosta/app-a"
    //     registryCredential = 'dockerhub'        
    // }

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

        stage('Build') {
            steps {
                sh "docker build -t giovanacosta/app-a:latest /var/lib/jenkins/workspace/pipeline-jenkins/Lab-Jenkins/app-a"
            }
        }

        // stage('Build das imagens Docker') {
        //     steps {
        //         script {
        //             dockerappa = docker.build("giovanacosta/app-a:latest", '-f ./Lab-Jenkins/app-a .')
        //             dockerappb = docker.build("giovanacosta/app-b:latest", '-f ./Lab-Jenkins/app-b .')
        //             dockerappc = docker.build("giovanacosta/app-c:latest", '-f ./Lab-Jenkins/app-c .')
        //             dockerappd = docker.build("giovanacosta/app-d:latest", '-f ./Lab-Jenkins/app-d .')
        //         }
        //     }
        // }

        // stage('Push imagem para o DockerHub') {
        //     steps {
        //         script {
        //             docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
        //                 dockerappa.push('latest')
        //                 dockerappb.push('latest')
        //                 dockerappc.push('latest')
        //                 dockerappd.push('latest')
        //             }
        //         }
        //     }
        // }
        // stage('Deploying App to Kubernetes') {
        //     steps {
        //         script {
        //             kubernetesDeploy(configs: "deploymentservice.yml", kubeconfigId: "kubernetes"                    
        //         }
        //     }
        // }
    }
}