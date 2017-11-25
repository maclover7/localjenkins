pipeline {
  agent any
  stages {
    stage('Ensure safe') {
      agent any
      steps {
        error 'CERTIFY_SAFE must be true.'
      }
    }
  }
}