pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
                bat 'msbuild helloworld.csproj /t:Build'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts 'Bin/**'
                }
                failure {
                    echo ' Deployment failed.'
                }
            }
        }
    }
}
