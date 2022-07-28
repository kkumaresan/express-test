pipeline {
  agent {
    docker {
      image 'node:16.13.1-alpine'
    }
  }
  environment {
    // COMMIT_TAG = getCommitTag()
    def dockerHome = tool 'myDocker'
    PATH = "${dockerHome}/bin:${PATH}"
  }
  stages {
    stage('Test') {
      steps {
        sh 'node --version'
      }
    }
  }
}