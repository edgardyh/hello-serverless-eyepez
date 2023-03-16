pipeline{
    agent
    agent {
        docker {
          image 'node:14-alpine'
        }
     }
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