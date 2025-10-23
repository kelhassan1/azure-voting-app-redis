pipeline {
    agent any 

    stages{
        stage('Verify branch'){
            steps{
                echo "$GIT_BRANCH"
            }
        }
        stage('Docker Build') {
            steps{
                sh(script: 'docker-compose build')
            }
        }
    }
}