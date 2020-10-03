pipeline {

    agent any

    stages{       
        stage('Build and Push to Docker Registry'){
            steps{
                script {
                    docker.withRegistry("https://docker-registry.demo.axway.com/","dssdocker"){
                        def dockerImage = docker.build("other-demo/paymentservice:${env.BUILD_ID}")
                        dockerImage.push()
                    }
                 }
            }
        }
    }
    post {
            cleanup {
                deleteDir()
            }
        }
}
