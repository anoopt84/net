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

        bat "\"${MSBUILD}\" net.sln /t:restore /nologo /nr:false /p:Configuration=\"release\" /p:Platform=\"Any CPU\""

            }
        }
    }
}
