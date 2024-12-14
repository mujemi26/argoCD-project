pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'dev') {
                        sh 'kubectl apply -f manifests/dev/deployment.yaml'
                    } else if (env.BRANCH_NAME == 'staging') {
                        sh 'kubectl apply -f manifests/staging/deployment.yaml'
                    } else if (env.BRANCH_NAME == 'production') {
                        sh 'kubectl apply -f manifests/production/deployment.yaml'
                    }
                }
            }
        }
    }
}
