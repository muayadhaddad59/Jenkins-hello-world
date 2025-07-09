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
        archiveArtifacts 'target/hello-world-*.jar'
      }
    }

    stage('Unit Test') {
      steps {
        script {
          for (int i = 0; i < 60; i++) {
            echo "${i + 1}"
            sleep 1
          }
          sh 'mvn test'
        }

        junit(testResults: 'trget/surefire-reports/TEST-*.xml', keepProperties: true, keepTestNames: true)
      }
    }

  }
  tools {
    maven 'M3910'
  }
}