pipeline {
    agent any
    stages {
      stage ('Build Docker'){
        steps {
            sh 'docker build -t anfelipe32/cichallenge:latest .'
        }
      }
      stage ('Publish'){
        steps{
        withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
      sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
      sh 'docker push anfelipe32/cichallenge:latest'
        }
      }
    }
    }
}
