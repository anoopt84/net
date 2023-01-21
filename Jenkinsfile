pipeline {
    agent any
    environment {
        dotnet = 'C:\\Program Files\\dotnet\\dotnet.exe'
    }
    stages {
        stage('Build Stage') {
            steps {
                bat 'dotnet build %WORKSPACE%\\net.sln --configuration Release'
            }
        }
        stage("Release Stage") {
            steps {
                bat 'dotnet build %WORKSPACE%\\net.sln /p:PublishProfile=" %WORKSPACE%\\net\\Properties\\PublishProfiles\\FolderProfile.pubxml" /p:Platform="Any CPU" /p:DeployOnBuild=true /m /p:DeleteExistingFiles=true /p:publishUrl=\\\\localhost\\C$\\inetpub\\wwwroot\\net'
            }
        }
    }
}
