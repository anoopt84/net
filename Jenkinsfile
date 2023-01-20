pipeline {
  
  agent any

  environment {
        MSBUILD = "C:\\Program Files\\Microsoft Visual Studio\\2022\\Community\\Msbuild\\Current\\Bin\\MSBuild.exe"
        CONFIG = 'Release'
        PLATFORM = 'x86'
    }
  
  stages {


        stage('Build') {
      steps {
        bat "dotnet net.csproj"

        bat "\"${MSBUILD}\" net.sln /p:Configuration=${env.CONFIG} /p:AppxBundlePlatforms=${env.PLATFORM}  /p:AppxBundle=Never /p:UapAppxPackageBuildMode=Sideloading  /p:AppxPackageSigningEnabled=false"

            }
      post{
          always {
           archiveArtifacts artifacts: '**/*.msix', followSymlinks: false
                }
            }
        }
    }
}
