pipeline {
    agent none
    stages {
    stage ('checkout'){
      steps{
          sh 'checkout scm'
      }
    }
      stage ('Build Docker'){
        steps{
            sh 'build docker -t clarke32/cichallenge:latest .'
        }
      }
        stage('Example') {
            steps {
                sh 'echo "Hello World!"'
            }
        }
        stage('Deliver'){
          steps{
              input message: 'Finished using the web site? (Click "Proceed" to continue)'
          }
        }
    }
}
