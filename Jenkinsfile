pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven 'M3910'
    }

    stages {
        stage('Echo Version') {
            steps {
                sh 'echo Print Maven Version'
                sh 'mvn -version'
            }
        }

        stage('Build') {
            steps {
                //  git branch: 'main', url: 'https://github.com/muayadhaddad59/Jenkins-hello-world.git'
                // /src/branch/main/src/main/java/com/kodekloud/hello_demo/HelloController.java

                // run maven package
                sh 'mvn clean package -DskipTests=true'
            }
        }

        stage('Unit Test') {
            steps {
                script{
                for (int i = 0; i < 60; i++) {
                    echo "${i + 1}"
                    sleep 1
                }
                sh 'mvn test'
            }
         }
        }
    }
}
