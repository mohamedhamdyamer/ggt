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
            agent {
                label 'agent-03'
            }
            steps {
                sh 'cp default.conf nginx.conf Dockerfile /tmp/ggt'
                sh "ssh amer@192.168.8.186 'pwd'"
                echo "container deployed! ..."
            }
        }
    }
}
