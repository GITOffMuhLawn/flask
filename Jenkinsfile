pipeline {
  agent any
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/GITOffMuhLawn/flask', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t jdoyle4/flask_app .'
      }
    }

    stage('Docker Login') {
      steps {
        sh '''docker login -u jdoyle4 -p dckr_pat_BotKBwwTRBMjJcvmYJtXrNha1vQ
'''
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push jdoyle4/flask_app'
      }
    }

  }
}