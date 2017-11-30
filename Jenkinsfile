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
            realtimeJUnit(testResults: 'resultados', allowEmptyResults: true, keepLongStdio: true)
          }
        }
        stage('estadoparalelo') {
          steps {
            echo 'empieza el estado'
            ansiblePlaybook(playbook: '/tmp/apache.yml', credentialsId: 'root', dynamicInventory: true, colorized: true)
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