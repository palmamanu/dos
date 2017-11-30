pipeline {
  agent {
    docker {
      image 'node'
      args '-u root'
    }
    
  }
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building...'
            sh 'npm install'
            task 'tarea1'
            pwd(tmp: true)
          }
        }
        stage('estadoparalelo') {
          steps {
            echo 'empieza el estado'
            ansiblePlaybook(playbook: 'apache.yml', colorized: true)
            pwd(tmp: true)
          }
        }
      }
    }
    stage('Test') {
      steps {
        echo 'Testing...'
      }
    }
    stage('Testeadoya') {
      steps {
        echo 'Testing...'
      }
    }
  }
}