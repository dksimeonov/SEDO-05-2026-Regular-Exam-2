pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Restore') {
            steps {
                sh 'dotnet restore Homies.sln'
            }
        }

        stage('Build') {
            steps {
                sh 'dotnet build Homies.sln --configuration Release --no-restore'
            }
        }

        stage('Test') {
            steps {
                sh 'dotnet test Homies.sln --configuration Release --no-build --verbosity normal'
            }
        }
    }
}