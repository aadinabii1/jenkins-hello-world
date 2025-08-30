pipeline {
  agent any
  stages {
    stage('Echo Version') {
      steps {
        sh 'echo Print Maven Version'
        sh 'mvn -version'
      }
    }

    stage('Build') {
      steps {
        sh 'mvn clean package -DskipTests=true'
        archiveArtifacts 'target/hello-demo-*.jar'
      }
    }

    stage('Unit Test') {
      steps {
        script {
          for (int i = 0; i < 60; i++) {
            echo"${i + 1}"
            sleep 1
          }
          sh "mvn test"
        }

      }
    }

  }
  tools {
    maven 'M3911'
  }
}