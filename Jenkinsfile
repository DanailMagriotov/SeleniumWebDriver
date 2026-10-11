pipeline{
    agent any
    stages{
        stage("Restore the project"){
            steps{
                bat "dotnet restore"
            }
        }
        stage("Build the project"){
            bat "dotnet build --no-restore"
        }
        stage("Run the tests in parallel"){
            parallel{
                stage("Run Project 1 tests"){
                    steps{
                        bat "dotnet test TestProject1/TestProject1.csproj --no-build --no-restore"
                    }
                }
                stage("Run Project 2 tests"){
                    steps{
                        bat "dotnet test TestProject2/TestProject2.csproj --no-build --no-restore"
                    }
                }
                stage("Run Project 3 tests"){
                    steps{
                        bat "dotnet test TestProject3/TestProject3.csproj --no-build --no-restore"
                    }
                }
            }
        }  
    }
}