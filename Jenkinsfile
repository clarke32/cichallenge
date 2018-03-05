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
                 sh 'npm install'
             }
        }
        stage('Test'){
            steps{
              sh 'npm test'
            }
        }
        stage('Docker Push') {
          agent any
          steps {
            withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
            sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
            sh 'docker push shanem/spring-petclinic:latest'
            }
          }
        }
        stage('Deliver'){
          steps{
              input message: 'Finished using the web site? (Click "Proceed" to continue)'
          }
        }
    }
}
