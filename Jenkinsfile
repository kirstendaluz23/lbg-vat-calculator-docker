pipeline{
 environment {
 registry = "kirstendaluz/vatcal"
        registryCredentials = "dockerhub_id"
        dockerImage = ""
    }
    agent any
        stages {
            stage ('Build Docker Image'){
                steps{
                    script {
                        dockerImage = docker.build(registry)
                    }
                }
            }

            stage ("Push to Docker Hub"){
                steps {
                    script {
                        docker.withRegistry('', registryCredentials) {
