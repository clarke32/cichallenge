pipeline {
    agent { dockerfile true }
    stages {
        stage('Example') {
            steps {
                sh 'echo "Hello World!"'
            }
        }
        stage ('Build'){
            steps {
                 sh 'sudo npm install'
             }
        }
        stage('Test'){
            steps{
              sh 'sudo npm test'
            }
        }
        stage('Deliver'){
          steps{
              input message: 'Finished using the web site? (Click "Proceed" to continue)'
          }
        }
    }
}
