pipeline {
    agent { label 'jenkins-agent'}

    stages{
        stage('Verify branch'){
            steps{
                echo "$GIT_BRANCH"
            }
        }
        stage('Docker Build') {
            steps{
                sh 'docker-compose build'
            }
        }
    }
}