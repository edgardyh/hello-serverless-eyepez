pipeline{
    agent any
    stages{
        stage('build'){
            steps{
                sh 'npm install'
            }
        }
        stage('buid'{
            steps{
                nodejs(nodeJSInstallationName: 'nodejs') {
                    withAWS(credentials: 'aws-credemtials') {
                        sh 'servless deploy'
                    }
                }
            }
        })
    }
}