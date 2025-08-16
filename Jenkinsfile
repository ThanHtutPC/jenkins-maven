pipeline {
    agent any 
    stages { 
        stage('Build') {
            steps {
                sh 'echo "building project..."'
            }
        }
        stage('Run Script') {
            steps {
                // Execute a shell script
                sh 'chmod a+x app.sh'
                sh './app.sh'
            }
        }
    }
}