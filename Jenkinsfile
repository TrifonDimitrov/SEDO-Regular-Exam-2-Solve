pipeline {
    agent any

    stages {
        stage('Restore the project') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build the project') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Test the project') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
