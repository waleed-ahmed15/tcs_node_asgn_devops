pipeline {
    environment {
    NPM_CONFIG_CACHE = "${WORKSPACE}/.npm"
    }
    agent {
        docker {
            image 'node:16'
            args '-p 3000:3000'
        }
    }
    stages {
        stage('Clone repository') {
            steps {
                git branch: 'master', url: 'https://github.com/waleed-ahmed15/tcs_node_asgn_devops.git'
            }
        }
        stage('Build application') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }
    }
}
