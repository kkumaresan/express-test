pipeline {
  agent any
  environment {
    COMMIT_TAG = getCommitTag()
  }
  tools { nodejs "node12" }
  stages{
    stage('Initialize'){
      def dockerHome = tool 'myDocker'
      env.PATH = "${dockerHome}/bin:${env.PATH}"
    }
    stage("Welcome") {
      steps {
        sh "npm install"
        sh "echo '${COMMIT_TAG} is built'"
      }
    }
    stage("Sec Block") {
      steps {
        withCredentials([string(credentialsId: 'sec-text', variable: 'dockerpwd')]) {
          sh "docker login -u kkumaresan -p ${dockerpwd}"
        }
      }
    }
  }
}

def getCommitTag() {
  def tag = sh script: 'git rev-parse HEAD', returnStdout: true
  return tag
}