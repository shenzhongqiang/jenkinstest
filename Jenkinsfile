/* Requires the Docker Pipeline plugin */
pipeline {
    agent any
    environment {
        http_proxy = 'http://127.0.0.1:10809'
        https_proxy = 'http://127.0.0.1:10809'
        no_proxy = 'localhost,127.0.0.1,github.com'
        apikey = credentials('apikey')
    }
    stages {
        stage('build') {
            steps {
                sh("curl -u ${apikey}:${apikey} https://example.com/")
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
        changed {
            echo "changed"
        }
    }
}
