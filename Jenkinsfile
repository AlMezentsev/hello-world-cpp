pipeline {
    agent {
        docker {
            image 'gcc:latest'
        }
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/AlMezentsev/hello-world-cpp.git'
            }
        }

        stage('Build') {
            steps {
                sh 'g++ -o main main.cpp'
            }
            post {
                success {
                    archiveArtifacts 'main'
                    echo 'Build successful.'
                }
                failure {
                    echo 'Build failed.'
                }
            }
        }
    }
}
