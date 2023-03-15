pipeline{
    agent any
    stages{
        stage('build') {
            steps{
                sh '/usr/bin/npm install'
            }
        }
        stage('deploy') {
            steps{
                nodejs(nodeJSInstallationName: 'nodejs') {
                    withAWS(credentials: 'aws-credentials') {
                        sh 'serverless deploy'
                    }
                }
            }
        }
    }
}