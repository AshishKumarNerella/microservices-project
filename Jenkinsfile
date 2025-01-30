pipeline {
    agent any
    stages {
        stage('BUILD') {
            steps {
                sh 'docker build -t ashishkumarnerella/frontendservice:v1'
            }
        }
        stage("PUSH") {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockerhub') {
                        sh 'docker push ashishkumarnerella/frontendservice:v1'
                    }
                }
            }
        }
     }  
}
}
