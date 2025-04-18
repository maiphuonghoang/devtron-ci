pipeline {
    agent any

    stages {
        stage('Clone stage') {
            steps {
                echo 'Hello world! Integrate GitLab & Jenkins'
            }
        }

        stage('Docker Build stage') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
                        sh 'docker build -f backend/Dockerfile -t maiphuonghoang/jenkins-pipeline-project:v1.0 backend/'
                        sh 'docker push maiphuonghoang/jenkins-pipeline-project:v1.0'
                    }
                }
            }
        }
    }
}
