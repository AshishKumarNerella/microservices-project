pipeline {
    agent any
    stages {
        stage('BUILD') {
            steps {
                sh 'docker build -t ashishkumarnerella/emailservice:v1 .'
            }
        }
        stage("PUSH") {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockerhub') {
                        sh 'docker push ashishkumarnerella/emailservice:v1'
                    }
                }
            }
        }
     }  
}

