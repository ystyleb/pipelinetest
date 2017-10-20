pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('1') {
          steps {
            echo 'building'
          }
        }
        stage('2') {
          steps {
            echo '2'
          }
        }
      }
    }
    stage('test') {
      steps {
        junit(allowEmptyResults: true, healthScaleFactor: 6, keepLongStdio: true, testResults: 'junit.results')
      }
    }
    stage('email') {
      steps {
        emailext(subject: 'test', body: 'test')
      }
    }
  }
}