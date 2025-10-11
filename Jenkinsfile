pipeline {
    agent any

    environment {
        KUBECONFIG_CREDENTIAL_ID = 'k8-token' // Jenkins credential ID
    }

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeConfig([credentialsId: "${env.k8-token"]) {
                    sh 'kubectl apply -f deployment-service.yml'
                }
            }
        }
    }
}
