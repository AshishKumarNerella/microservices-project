pipeline {
    agent any
    stages {
        stage('BUILD') {
            steps {
                sh 'docker build -t ashishkumarnerella/paymentservice:v1'
            }
        }
        stage("PUSH") {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockerhub') {
                        sh 'docker push ashishkumarnerella/paymentservice:v1'
                    }
                }
            }
        }
     }  
}

