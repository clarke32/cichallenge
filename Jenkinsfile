pipeline {
    agent any
    stages {
      stage ('Build Docker'){
        steps {
            sh 'docker build -t clarke32/cichallenge:latest .'
        }
      }
    }
}
