// Derive environment from branch names.
AGENT_TAG = "${env.BRANCH_NAME == 'main' ? 'plexcdpapp01' : (env.BRANCH_NAME ==~ /^release-\d+$/ ? 'qlexcdpapp01' : 'linux')}"

pipeline {
  agent {
      label AGENT_TAG
    }
  stages {
    stage('Hello') {
      steps {
        echo "Building on ${AGENT_TAG}"
        checkout scm
        dir('app') {
          sh 'composer install'
        }
      }
    }
  }
}
