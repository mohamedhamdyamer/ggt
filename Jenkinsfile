pipeline {
    agent {
        label 'agent-01'
    }

    stages {
        stage('append-env') {
            steps {
                sh 'cat index.html'
            }
        }
    }
}
