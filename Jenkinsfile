pipeline {
  agent {
    docker {
      image 'node:12'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Install packages') {
      steps {
        sh 'cd ./mingeso; npm -g install'
      }
    }

    stage('Test') {
      steps {
        sh 'cd ./mingeso; npm run test -- --coverage --watchAll=false'
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