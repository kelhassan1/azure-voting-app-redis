pipeline {
    agent { label 'jenkins-agent'}

    stages{
        stage('Debug PATH') {
        steps {
                sh 'echo $PATH'
                sh 'which docker'
                sh 'docker --version'
                sh 'docker compose version'
            }
        }
        stage('Verify branch'){
            steps{
                echo "$GIT_BRANCH"
            }
        }
        stage('Docker Build') {
            steps{
                sh 'docker compose build'
            }
        }
    }
}