pipeline {
    agent any
    tools {nodejs "node13"}

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '78ce21d6-0656-465b-bf20-ad352b8d66ab', url: 'https://github.com/devchloe/demo-vue.git']]])
            }
        }
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }
    }

    post {
        always {
            archiveArtifacts 'dist/**/**'

        }
    }
}
