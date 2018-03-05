pipeline {
    agent { dockerfile true }
    stages {
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
