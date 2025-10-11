pipeline {
    agent any

   
    stages {
        stage('Deploy To Kubernetes') {
            steps {
               kubeconfig(credentialsId: 'k8-token', serverUrl: 'https://2F94A4306FAD26A96F10D35D827BFE25.gr7.us-east-1.eks.amazonaws.com') {
                    sh 'kubectl apply -f deployment-service.yml'
                }
            }
        }
    }
}
