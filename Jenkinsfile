pipeline {
    agent any
    stages{
        stage("Dotnet restore"){
            when{
                anyOf{
                    branch "develop"
                    branch "feature/*"
                }
            }
            steps{
                bat "dotnet restore"
            }
        }
        stage("Dotnet build"){
            steps{
                bat "dotnet build --no-restore"
            }
            when{
                anyOf{
                    branch "main"
                    branch "feature/*"
                }
            }
        }
        stage("Dotnet test"){
            steps{
                bat "dotnet test --no-build --verbosity normal"
            }
            when{
                anyOf{
                    branch "develop"
                    branch "feature/*"
                }
            }
        }
    }
} format this file