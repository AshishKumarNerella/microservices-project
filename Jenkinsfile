pipeline {
    agent any
    stages {
        stage('BUILD') {
            steps {
                sh 'docker build -t ashishkumarnerella/productcatalogservice:v1'
            }
        }
        stage("PUSH") {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockerhub') {
                        sh 'docker push ashishkumarnerella/productcatalogservice:v1'
                    }
                }
            }
        }
     }  
}

