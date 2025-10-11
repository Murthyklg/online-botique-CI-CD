pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
               kubeconfig(caCertificate: 'eyJhbGciOiJSUzI1NiIsImtpZCI6IlJPeTFEMDZ6ejJHY0pyRnJYcVRlVFVyZVV5b0drc1l0QnZSa3ctTTgwamsifQ.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJ3ZWItYXBwcyIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VjcmV0Lm5hbWUiOiJteXNlY3JldG5hbWUiLCJrdWJlcm5ldGVzLmlvL3NlcnZpY2VhY2NvdW50L3NlcnZpY2UtYWNjb3VudC5uYW1lIjoiamVua2lucyIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VydmljZS1hY2NvdW50LnVpZCI6ImQ0NDE0Yzk2LWVhZGYtNGUzOC1hOWM4LTc3NTE2MzJiMzRiZiIsInN1YiI6InN5c3RlbTpzZXJ2aWNlYWNjb3VudDp3ZWItYXBwczpqZW5raW5zIn0.Xj9au9E3egRoRARe0uezA6ueyUoVnL9rpah82y9fCLbU7UaFZb-NG9rbaEPLYclZVlKiI4Hr5zqQUZ42xjx0gzUDfSvNJdmlOerVdhYt8XXQfcQqhUwqy5PyIkqw0PExNDIYkI8nm92HArHox_SXG-MhHN75Q3HZxTBBNsUfNXG3Hvhzak3A_l2NyEmtKNNYeS59JKHNr1l9xFQq9t2kL7OlPTkj6JsL8ayPExejMPP8tpZMsgFcJmUc6vtKWWYdwaMMlcNeDk7d3fySgl7QwFcZdWPtazY8ISoXyaA2_wOism00yMTVy9Gt2hFQs-hhIgucY_mIzORsumcKGEGR_g', credentialsId: 'k8-token', serverUrl: 'https://2F94A4306FAD26A96F10D35D827BFE25.gr7.us-east-1.eks.amazonaws.com') { 
                    sh "kubectl apply -f deployment-service.yml"
                    
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                 kubeconfig(caCertificate: 'eyJhbGciOiJSUzI1NiIsImtpZCI6IlJPeTFEMDZ6ejJHY0pyRnJYcVRlVFVyZVV5b0drc1l0QnZSa3ctTTgwamsifQ.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJ3ZWItYXBwcyIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VjcmV0Lm5hbWUiOiJteXNlY3JldG5hbWUiLCJrdWJlcm5ldGVzLmlvL3NlcnZpY2VhY2NvdW50L3NlcnZpY2UtYWNjb3VudC5uYW1lIjoiamVua2lucyIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VydmljZS1hY2NvdW50LnVpZCI6ImQ0NDE0Yzk2LWVhZGYtNGUzOC1hOWM4LTc3NTE2MzJiMzRiZiIsInN1YiI6InN5c3RlbTpzZXJ2aWNlYWNjb3VudDp3ZWItYXBwczpqZW5raW5zIn0.Xj9au9E3egRoRARe0uezA6ueyUoVnL9rpah82y9fCLbU7UaFZb-NG9rbaEPLYclZVlKiI4Hr5zqQUZ42xjx0gzUDfSvNJdmlOerVdhYt8XXQfcQqhUwqy5PyIkqw0PExNDIYkI8nm92HArHox_SXG-MhHN75Q3HZxTBBNsUfNXG3Hvhzak3A_l2NyEmtKNNYeS59JKHNr1l9xFQq9t2kL7OlPTkj6JsL8ayPExejMPP8tpZMsgFcJmUc6vtKWWYdwaMMlcNeDk7d3fySgl7QwFcZdWPtazY8ISoXyaA2_wOism00yMTVy9Gt2hFQs-hhIgucY_mIzORsumcKGEGR_g', credentialsId: 'k8-token', serverUrl: 'https://2F94A4306FAD26A96F10D35D827BFE25.gr7.us-east-1.eks.amazonaws.com') {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}
