pipeline {
  agent any
  stages {
    stage('Code Collection') {
      steps {
        git(url: 'https://github.com/TheDevrajDas/simpleMavenJunit.git', branch: 'master', changelog: true, poll: true)
      }
    }

    stage('Complie code') {
      steps {
        sh '''mvn clean




'''
        sh 'mvn compile'
      }
    }

    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }

    stage('Test report') {
      steps {
        junit '**/target/sure-fire/*.xml'
      }
    }

  }
}