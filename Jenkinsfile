pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                git branch: 'main', url: 'https://github.com/jeanpierrenisingizwe/Jenkins.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                bat 'dir'
                bat 'dotnet build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'dotnet test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                bat 'xcopy /Y /E build\\* D:\\Deploy\\'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
        always {
            echo 'Cleaning up workspace...'
        }
    }
}
