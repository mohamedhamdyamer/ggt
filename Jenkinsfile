pipeline {
    agent {
        label 'agent-01'
    }
    
    stages {
        stage('append-env') {
            agent {
                label 'agent-01'
            }
            steps {
                sh 'cat index.html'
            }
        }
    }
}
