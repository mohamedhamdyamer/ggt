pipeline {
    agent {
        label 'agent-01'
    }
    
    stages {

        stage('init') {
            agent {
                label 'agent-01'
            }
            steps {
                echo 'Initializing ...'
            }
        }

        stage('build') {
            parallel {
                stage('build-linux') {
                    agent {
                        label 'agent-02'
                    }
                    steps {
                        echo 'Building on Linux ...'
                    }
                }
                stage('build-win') {
                    agent {
                        label 'agent-03'
                    }
                    steps {
                        echo 'Building on Windows ...'
                    }
                }
            }
        }
    }
}
