pipeline {
  agent any

  options {
    ansiColor('xterm')
  }

  parameters {
    string(name: 'ENV', defaultValue: 'prod', description: 'Environment')
    string(name: 'APPNAME', defaultValue: '', description: 'Environment')
  }

  stages {

    stage('Get KubeConfig') {
      steps {
        sh 'aws eks update-kubeconfig --name ${ENV}-roboshop'
      }
    }

    stage('Get App Code') {
      steps {
        dir('APP') {
          git branch: 'main', url: 'https://github.com/raghudevopsb74/${APPNAME}'
        }
        sh 'ls -l '
      }
    }


  }
}