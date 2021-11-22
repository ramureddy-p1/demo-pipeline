pipeline {
  agent any
  stages {
    stage('Build stage') {
      steps {
        echo 'Build demo-app'
        sh 'sh run_build_script.sh'
      }
    }

    stage('Linux Tests Stage') {
      parallel {
        stage('Linux Tests Stage') {
          steps {
            echo 'Run linux tests'
            sh 'sh run_linux_tests.sh'
          }
        }

        stage('Windows Tests Stage') {
          steps {
            echo 'Run windows test'
          }
        }

      }
    }

    stage('Deploy a Staging Stage') {
      steps {
        echo 'Deploy to staging environment'
        input 'Ok to deploy to production'
      }
    }

    stage('Deploy Production') {
      steps {
        echo 'Deploy to Prod'
      }
    }

  }
}