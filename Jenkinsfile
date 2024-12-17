pipeline {
    agent any

    stages {
        stage('Deploy to kubernetes') {
            steps {
            withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: ' EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://E15C01E88D287C493A19A83617F0B8C7.gr7.ap-south-1.eks.amazonaws.com']]) {
              sh "kubectl apply -f deployment-service.yml "
            }
            }
        }
        stage('verify Deployment') {
            steps {
            withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: ' EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://E15C01E88D287C493A19A83617F0B8C7.gr7.ap-south-1.eks.amazonaws.com']]) {
            sh  "kubectl get svc -n webapps"
}
        }
        
    }
}
}


