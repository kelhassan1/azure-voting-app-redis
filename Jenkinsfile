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
        stage('Run Tests') {
            steps{
                sh(script: 'pytest ./tests/test_sample.py')
            }
            post{
                success{
                    echo "test passed! :) "
                }
                failure{
                    echo "test failed :("
                }
            }
        }
    }
    post{
        always{
            sh(script: 'docker-compose down')
        }
    }
}