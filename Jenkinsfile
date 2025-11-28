pipeline {
agent any  // Runs on any available agent

```
tools {
    // Optional: define any tools if installed (e.g., JDK)
    // jdk 'JDK11'
}

environment {
    // Optional: add any environment variables
    // EXAMPLE_VAR = "value"
}

stages {
    stage('Checkout SCM') {
        steps {
            // Checkout your Git repository
            git branch: 'main', url: 'https://github.com/jeanpierrenisingizwe/Jenkins.git'
        }
    }

    stage('Build') {
        steps {
            echo 'Building the project...'
            bat 'dir'  // Example Windows command
            // Add your actual build commands here, e.g.:
            // bat 'msbuild MyProject.sln'
        }
    }

    stage('Test') {
        steps {
            echo 'Running tests...'
            // Add your test commands here, e.g.:
            // bat 'vstest.console.exe MyTests.dll'
        }
    }

    stage('Deploy') {
        steps {
            echo 'Deploying...'
            // Add your deployment commands here, e.g.:
            // bat 'copy /Y build\\output\\* D:\\Deploy\\'
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
}
```

}
