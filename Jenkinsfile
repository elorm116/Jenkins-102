pipeline {
    agent any  // Use the Jenkins host directly
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t my-app:latest .'
            }
        }
        stage('Run') {
            steps {
                sh 'docker stop my-app || true'
                sh 'docker rm my-app || true'
                sh 'docker run -d --name my-app -p 3000:3000 my-app:latest'
                // Removed 'docker run my-app:latest' - see note below
            }
        }
    }
}
