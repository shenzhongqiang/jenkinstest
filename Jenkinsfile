/* Requires the Docker Pipeline plugin */
pipeline {
    agent any
    environment {
        http_proxy = 'http://127.0.0.1:10809'
        https_proxy = 'http://127.0.0.1:10809'
        no_proxy = 'localhost,127.0.0.1,github.com'
        apikey = credentials('apikey')
    }
    parameters {
        string(name: 'Greeting', defaultValue: 'Hello', description: 'How should I greet the world?')
    }
    stages {
        stage('build') {
            steps {
                echo "${params.Greeting} world"
                sh 'pwd'
                sh './deploy.sh'
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
