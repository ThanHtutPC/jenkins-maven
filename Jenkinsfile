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
        stage('Test') {
            parallel {
                stage('Test on windows') {
                    steps{ 
                        echo "This is testing for windows"
                    }
                }
                stage('Test on linux') {
                    steps{
                        echo "This is testing for linux"
                    }
                }
            }
        }
        stage('Confirm deploy or staging') {
            steps{ 
                timeout(time: 60, unit: 'SECONDS') {
                    input(message: 'Okay next step?', ok: 'Let\'s Do it!')
                }
            }
        }
        stage('Deploy to staging') {
            steps{ 
                echo 'deploying process is ok' 
            }
        }
        stage('Confirm Deploy or prod') {
            steps{
                timeout(time: 20, unit: 'SECONDS') {
                    input(message: "Are you ready to run prod", ok: "run next step")
                }
            }
        }
        stage('Deploy to prod') {
            steps{
                sh 'chmod a+x test_app.sh'
                sh './test_app.sh'
            }
        }
    }
    post{
        success {
            echo "everything is done"
        }
        aborted {
            echo "re-run this code"
        }
        failure {
            echo "check your code or pipeline"
        }
    }
}