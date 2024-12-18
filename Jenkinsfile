pipeline {
    agent any  // This runs the pipeline on any available Jenkins agent

    stages {
        stage('deploy to k8') {
            steps {
                script {
                  kubernetesDeploy (configs: 'deployment.yaml',kubeconfigId: 'k8sconfigpwd')
                    // The echo command will print "Hello, World!" to the console
                    echo 'Hello, World!'
                }
            }
        }

       stage('deploy to k8-service') {
            steps {
                script {
                  kubernetesDeploy (configs: 'service.yaml',kubeconfigId: 'k8sconfigpwd')
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
