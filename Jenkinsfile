pipeline {
  agent any
  environment {
    PATH = "/usr/local/bin/npm:$PATH"
  }
  stages{
    stage("Welcome") {
      steps {
        sh "/usr/local/bin/npm install"
      }
    }
  }
}