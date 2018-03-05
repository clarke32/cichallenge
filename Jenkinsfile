pipeline {
    agent any
    stages {
      stage ('Build Docker'){
        steps {
            sh 'build docker -t clarke32/cichallenge:latest .'
        }
      }
    }
}
