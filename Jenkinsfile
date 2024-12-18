pipeline {
    agent any  // This runs the pipeline on any available Jenkins agent

    stages {
        stage('deploy to k8') {
            steps {
                script {
                    
                     withCredentials([file(credentialsId: 'KUBERNETES-CREDENTIALS'	, variable: 'KUBECONFIG')]) {
                        // Run kubectl commands inside the pipeline to interact with Kubernetes
                        sh 'kubectl get pods'  // Replace with the path to your Kubernetes deployment YAML
                        sh 'kubectl apply -f deployment.yaml '
                        
                    }
                    // The echo command will print "Hello, World!" to the console
                    echo 'Hello, World!'
                }
            }
        }

       stage('deploy to k8-service') {
            steps {
                script {
                     withCredentials([file(credentialsId: 'KUBERNETES-CREDENTIALS'	, variable: 'KUBECONFIG')]) {
                        // Run kubectl commands inside the pipeline to interact with Kubernetes
                        sh 'kubectl get pods'  // Replace with the path to your Kubernetes deployment YAML
                        sh 'kubectl apply -f service.yaml '
                        
                    }
                    // The echo command will print "Hello, World!" to the console
                    echo 'Hello, World!'
                }
            }
        }
    }

    post {
        always {
            // A simple message that runs after the pipeline has finished
            echo 'Pipeline has finished!'
        }
    }
}
