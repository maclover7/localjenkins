pipeline {
  agent any
  parameters {
    boolean(name: "CERTIFY_SAFE", defaultValue: false)
  }
  stages {
    stage('Ensure safe') {
      parallel {
        stage('Ensure safe') {
          agent any
          steps {
            script {
              if (!env.CERTIFY_SAFE) {
                error("CERTIFY_SAFE must be true") }
              }
              
            }
          }
          stage('aix run tests') {
            steps {
              sh 'echo \'hi\''
            }
          }
          stage('linux run tests') {
            steps {
              sh 'echo \'hi2\''
            }
          }
        }
      }
    }
    environment {
      CERTIFY_SAFE = 'true'
    }
  }
