pipeline {
    agent {
        label 'agent-01'
    }

    stages {
        stage('copy-to-tmp-location') {
            steps {
                sh 'cp index.html /tmp/ggt/index.html'
            }
        }
        stage('append-details') {
            agent {
                label 'agent-02'
            }
            steps {
                sh "sed -i 's/Environment built for:/Environment built for: Jenkins Testing .../g' /tmp/ggt/index.html"
                sh "sed -i 's/Build Number:/Build Number: $BUILD_NUMBER/g' /tmp/ggt/index.html"
            }
        }
        stage('deploy-container') {
            steps {
                echo "container deployed! ..."
            }
        }
    }
}
