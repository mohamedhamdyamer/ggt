pipeline {
    agent {
        label 'agent-01'
    }

    stages {
        stage('append-env') {
            steps {
                sh 'cat index.html'
                sh "sed -i 's/Environment built for:/Environment built for: Jenkins Testing .../g' index.html"
                sh 'cat index.html'
            }
        }
    }
}
