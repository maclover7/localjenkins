pipeline {
  agent any
  parameters {
    booleanParam(name: "CERTIFY_SAFE", defaultValue: false)
  }
  stages {
    stage('Ensure safe') {
      parallel {
        stage('Ensure safe') {
          agent any
          steps {
            script {
              if (!params.CERTIFY_SAFE) {
                error("CERTIFY_SAFE must be true") }
              }
              
            }
          }
          stage('aix run tests') {
            steps {
              sh 'echo \'hi\''
            }
            
            post {
              success {
                sh 'echo "aix success"'
              }
            }
          }
          stage('linux run tests') {
            steps {
              sh 'echo \'hi2\''
            }
            post {
              success {
                sh 'echo "linux success"'
              }
            }
          }
        }
      }
    }
  }
