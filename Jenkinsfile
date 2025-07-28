/* Requires the Docker Pipeline plugin */
pipeline {
    agent { docker { image 'python:3.13.5-alpine3.22' } }
    environment {
        http_proxy = 'http://127.0.0.1:10809'
        https_proxy = 'http://127.0.0.1:10809'
        no_proxy = 'localhost,127.0.0.1,github.com'
    }
    stages {
        stage('build') {
            steps {
                retry(3) {sh 'pythonabc --version'}
            }
        }
    }
    post {
        always {
            echo "always"
        }
        success {
            echo "success"
        }
        failure {
            echo "failure"
        }
    }
}
