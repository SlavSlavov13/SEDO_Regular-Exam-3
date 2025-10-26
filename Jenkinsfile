pipeline {
    agent {
        docker { 
            image 'mcr.microsoft.com/dotnet/sdk:8.0'
        }
    }

    stages {  

        stage('Build the application') {
            when {
                branch 'main'
            }
            steps {
                echo 'Building...'
                sh 'dotnet build'
            }
        }
        
        stage('Run the Tests') {
            when {
                branch 'main'
            }
            steps {
                echo 'Running Tests...'
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
