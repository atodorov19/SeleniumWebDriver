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
        stage('Test'){
            steps{
                bat 'dotnet test'
            }
        }
    }
}