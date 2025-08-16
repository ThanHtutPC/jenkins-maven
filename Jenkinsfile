pipeline {
    agent any 
    stages { 
        stages('Checkout') {
            steps {
                // Pull source code from the repository
                git branch: 'pipeline', url: 'git@github.com:ThanHtutPC/jenkins-maven.git'
            }
        }
        stages('Build') {
            steps {
                sh 'echo "building project..."'
            }
        }
        stages('Run Script') {
            steps {
                // Execute a shell script
                sh './app.sh'
            }
        }
    }
}