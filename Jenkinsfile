pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: '', namespace: '', serverUrl: 'https://87A6C7916D7E40606C1E9475D9490CC4.gr7.us-east-1.eks.amazonaws.com']]) {

                    sh "kubectl apply -f deployment-service.yml"
                }
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: '', namespace: '', serverUrl: 'https://87A6C7916D7E40606C1E9475D9490CC4.gr7.us-east-1.eks.amazonaws.com']]) {


                    sh "kubectl get svc -n webapps"
                }
                }
            }
        }
    }
}
