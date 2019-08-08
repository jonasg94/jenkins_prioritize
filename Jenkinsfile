pipeline {
  agent{
    node {
        label 'master'
        }
    }
  stages {
    stage('Post Build') {
      steps {
        sh 'sleep 100'
        echo 'Cleaning Workspace...'

        dir "${env.WORKSPACE}@libs"
        cleanWs notFailBuild: true

        dir "${env.WORKSPACE}@script"
        cleanWs notFailBuild: true

        dir "${env.WORKSPACE}@script@tmp"
        cleanWs notFailBuild: true
      }
    }
  }
}


