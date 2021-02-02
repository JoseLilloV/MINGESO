pipeline {
  agent any
  stages {
    stage('Install packages') {
      steps {
        sh 'cd ./mingeso; npm install'
      }
    }

    stage('Linter') {
      steps {
        sh 'cd ./mingeso; npm run lint'
      }
    }
    stage('Build/Deploy'){
      steps {
        sh 'cd ./mingeso; npm run build'
      }
    }
  }
  environment {
    CI = 'true'
  }
}