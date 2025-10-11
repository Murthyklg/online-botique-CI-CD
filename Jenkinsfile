pipeline {
    agent any

   
    stages {
        stage('Deploy To Kubernetes') {
            steps {
               withKubeConfig([credentialsId: 'k8-token']) {
                    sh 'kubectl apply -f deployment-service.yml'
                }
            }
        }
    }
}
