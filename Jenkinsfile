pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: 'eyJhbGciOiJSUzI1NiIsImtpZCI6Ikk5U0ZfNEVnckQzZk9vT3MwUXM0T0E4RnMwYUxUeldqbUt3TjRBckFNSXcifQ.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJ3ZWJhcHBzIiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZWNyZXQubmFtZSI6Im15c2VjcmV0bmFtZSIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VydmljZS1hY2NvdW50Lm5hbWUiOiJqZW5raW5zIiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZXJ2aWNlLWFjY291bnQudWlkIjoiMDNhNjczNzktODAzNy00NzY5LTk3NGItODcyODllZjMzZGJkIiwic3ViIjoic3lzdGVtOnNlcnZpY2VhY2NvdW50OndlYmFwcHM6amVua2lucyJ9.gFemrKR1t3LExklX-Gd7kuMoGPS6hTHp-cmI6toyNkdMbWf8i_aZqgH2RPSgu_-rSbStSCp9c0bQ_Iv_4E684RkzFLxIAslSGqDVpBn-X0G1sRTYh4f8QoNEZUW-2MZUX7RcjwgHvyrOC7bKhc9Yb7SBCCXetooU345L4330mxiUnuU3hEPsg5YUIPvkEr7WRpneFRbDi4T4JslaqBiQR2i-9bteXDHEr1eYqFi4zDnfGYEfZSpvgKG0XydLhpG74ipU-TJigitekEHvonnI4Y6Vdvka3asduXEHv82oN-63rG-vqQBU_JGsvQjQqeky_CpTBzdJSukHaNLD2HgqJg', clusterName: 'EKS-1',  credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://2F94A4306FAD26A96F10D35D827BFE25.gr7.us-east-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                    
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: 'eyJhbGciOiJSUzI1NiIsImtpZCI6Ikk5U0ZfNEVnckQzZk9vT3MwUXM0T0E4RnMwYUxUeldqbUt3TjRBckFNSXcifQ.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJ3ZWJhcHBzIiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZWNyZXQubmFtZSI6Im15c2VjcmV0bmFtZSIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VydmljZS1hY2NvdW50Lm5hbWUiOiJqZW5raW5zIiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZXJ2aWNlLWFjY291bnQudWlkIjoiMDNhNjczNzktODAzNy00NzY5LTk3NGItODcyODllZjMzZGJkIiwic3ViIjoic3lzdGVtOnNlcnZpY2VhY2NvdW50OndlYmFwcHM6amVua2lucyJ9.gFemrKR1t3LExklX-Gd7kuMoGPS6hTHp-cmI6toyNkdMbWf8i_aZqgH2RPSgu_-rSbStSCp9c0bQ_Iv_4E684RkzFLxIAslSGqDVpBn-X0G1sRTYh4f8QoNEZUW-2MZUX7RcjwgHvyrOC7bKhc9Yb7SBCCXetooU345L4330mxiUnuU3hEPsg5YUIPvkEr7WRpneFRbDi4T4JslaqBiQR2i-9bteXDHEr1eYqFi4zDnfGYEfZSpvgKG0XydLhpG74ipU-TJigitekEHvonnI4Y6Vdvka3asduXEHv82oN-63rG-vqQBU_JGsvQjQqeky_CpTBzdJSukHaNLD2HgqJg', clusterName: 'EKS-1',  credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://2F94A4306FAD26A96F10D35D827BFE25.gr7.us-east-1.eks.amazonaws.com']]) {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}
