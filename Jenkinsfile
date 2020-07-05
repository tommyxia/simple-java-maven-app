pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2'
    }
  }
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/tommyxia/ssiwo-ruoyi.git'
      }
    }
    stage('Compile') {
      steps {
        sh 'mvn compile'
      }
    }
    stage('Start') {
      steps {
        sh './ry.sh start'
        input 'start ruoyi'
      }
    }
  }
}
