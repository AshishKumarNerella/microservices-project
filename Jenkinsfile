pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'microservicescluster', contextName: '', credentialsId: 'secret', namespace: 'webapps', serverUrl: 'https://492837ACCC32930BDF2CB6F122B1C657.gr7.us-east-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                    
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'microservicescluster', contextName: '', credentialsId: 'secret', namespace: 'webapps', serverUrl: 'https://492837ACCC32930BDF2CB6F122B1C657.gr7.us-east-1.eks.amazonaws.com']]) {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}
