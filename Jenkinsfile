pipeline {
  
  agent any

  environment {
        MSBUILD = "C:\\Program Files\\Microsoft Visual Studio\\2022\\Community\\Msbuild\\Current\\Bin\\MSBuild.exe"
        CONFIG = 'Release'
        PLATFORM = 'x64'
    }
  
  stages {
        stage('Build') {
      steps {
        bat "dotnet restore net.csproj"

        bat "\"${MSBUILD}\" net.sln /nologo /nr:false /p:Configuration=Release /p:Platform=\"Any CPU\" /t:clean;restore;rebuild"

            }
      post{
          always {
           archiveArtifacts artifacts: '**/*.msix', followSymlinks: false
                }
            }
        }
    }
}
