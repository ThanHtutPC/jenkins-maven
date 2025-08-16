pipeline {
    agent any 
    stages { 
        stage('Build') {
            steps {
                // Execute a shell script
                sh 'chmod a+x app.sh'
                sh './app.sh'
            }
        }
    }
}