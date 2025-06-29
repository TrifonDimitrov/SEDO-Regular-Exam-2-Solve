pipeline {

    stages {
        stage('Check Branch') {
            when {
                branch 'main'
            }
            steps {
                echo "Running pipeline on branch: ${env.BRANCH_NAME}"
            }
        }
        stage('Restore the project') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build the project') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Test the project') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
