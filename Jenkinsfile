pipeline {
  agent any
  environment {
    PATH = "/usr/local/bin/npm:$PATH"
  }
  stages{
    stage("Welcome") {
      steps {
        sh "npm install"
      }
    }
  }
}