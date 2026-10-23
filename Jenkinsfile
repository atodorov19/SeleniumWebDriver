pipeline{ 
    
    agent any
    stages{
        stage('Restore dependencies'){
            steps{
                bat 'dotnet restore'
            }
        }
        stage('Build'){
            steps{
                bat 'dotnet build'
            }
        }
        stage("Run different project tests"){
            parallel{
                stage("Project1 tests"){
                    steps{
                        bat "dotnet test TestProject1/TestProject1.csproj --no-build --verbosity normal"
                    }
                }
                stage("Project2 tests"){
                    steps{
                        bat "dotnet test TestProject2/TestProject2.csproj --no-build --verbosity normal"
                    }
                }
                stage("Project3 tests"){
                    steps{
                        bat "dotnet test TestProject3/TestProject3.csproj --no-build --verbosity normal"
                    }
                }
            }
        }
    }
}