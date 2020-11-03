// Derive environment from branch names.
AGENT_TAG = "${env.BRANCH_NAME == 'main' ? 'lexbldlinux30' : (env.BRANCH_NAME ==~ /^release-\d+$/ ? 'lexbldlinux31' : 'lexbldlinux32')}"

pipeline {
  agent {
      label AGENT_TAG
    }
  stages {
    stage('Hello') {
      steps {
        echo "Building on ${AGENT_TAG}"
        sh "hostname"
        sh "pwd"
      }
    }
  }
}
