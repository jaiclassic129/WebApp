pipeline {
  agent any
  stages {
    stage('Dev Code Pull') {
      steps {
        echo 'Dev Code Pull'
      }
    }

    stage('Dev Maven Build') {
      steps {
        echo 'Dev Maven Build'
      }
    }

    stage('QA Deploy') {
      steps {
        echo 'QA Deploy'
      }
    }

    stage('QA Tests') {
      parallel {
        stage('QA Tests') {
          steps {
            echo 'QA Tests'
          }
        }

        stage('Web (Code Pull, Run tests)') {
          steps {
            echo 'Web (Code Pull, Run tests)'
          }
        }

        stage('API (Code Pull, Run tests)') {
          steps {
            echo 'API (Code Pull, Run tests)'
          }
        }

      }
    }

    stage('QA Certification') {
      steps {
        echo 'QA Certification'
        input 'Please Certify for QA'
      }
    }

    stage('UAT Deploy') {
      steps {
        echo 'UAT Deploy'
      }
    }

    stage('UAT Certification') {
      when {
        branch 'master'
      }
      steps {
        echo 'UAT Certification'
        input 'Please Certify for UAT'
      }
    }

    stage('Prod Deploy') {
      steps {
        echo 'Prod Deploy'
      }
    }

  }
}