pipeline    {
    agent any
    
    stages{
        stage('First Stage'){
            steps{
                echo 'Hi Haresh'
            }
        }
        stage('Building'){
            steps{
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
        }
        stage('final'){
            steps{
                echo "${env.JOB_NAME}"
            }
        }

    }   
    post {
        success {
            mail to:"${DEFAULT_RECIPIENTS}", subject:"SUCCESS: ${currentBuild.fullDisplayName}", body: "Yay, we passed."
        }
        failure {
            mail to:"${DEFAULT_RECIPIENTS}", subject:"FAILURE: ${currentBuild.fullDisplayName}", body: "Boo, we failed."
        }
    }   
}