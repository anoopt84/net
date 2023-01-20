pipeline {
  
  agent any

  environment {
        MSBUILD = "C:\\Program Files\\Microsoft Visual Studio\\2022\\Community\\Msbuild\\Current\\Bin\\MSBuild.exe"
        CONFIG = 'Release'
        PLATFORM = 'x64'
    }
  
  stages {

    stage ('Clean workspace') {
  steps {
    cleanWs()
  }
}

        stage('Build') {
      steps {
        bat "dotnet restore net.csproj"

        bat "\"${MSBUILD}\" net.sln /nologo /nr:false  /p:platform=\"x64\" /p:configuration=\"release\" /t:clean;restore;rebuild

            }
      post{
          always {
           archiveArtifacts artifacts: '**/*.msix', followSymlinks: false
                }
            }
        }
    }
}
