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
  }
}

def getCommitTag() {
  def tag = sh script: 'git rev-parse HEAD', returnStdout: true
  return tag
}