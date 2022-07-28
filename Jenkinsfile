pipeline {
  agent any
  environment {
    COMMIT_TAG = getCommitTag()
  }
  tools { nodejs "node12" }
  stages{
    stage("Welcome") {
      steps {
        sh "npm install"
        sh "echo '${COMMIT_TAG} is built'"
      }
    }
    stage("Sec Block") {
      steps {
        withCredentials([string(credentialsId: 'sec-text', variable: 'secc-texxt')]) {
          sh "This is the secret ${secc-texxt}"
        }
      }
    }
  }
}

def getCommitTag() {
  def tag = sh script: 'git rev-parse HEAD', returnStdout: true
  return tag
}