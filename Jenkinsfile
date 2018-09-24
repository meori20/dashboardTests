pipeline {
    agent any

    stages {
        stage ('Compile Stage') {
            tools {
                jdk "JDK8"
            }
            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn clean compile'
                }
            }
        }
        
        stage ('AWS Stage') {
            tools {
                jdk "JDK8"
            }
            steps {
                sh '''
                    curl "https://s3.amazonaws.com/aws-cli/awscli-bundle.zip" -o "awscli-bundle.zip"
                    unzip awscli-bundle.zip
                    apt-get install -y awscli
                '''
            }
        }

        stage ('Testing Stage') {
            tools {
                jdk "JDK8"
            }
            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn test'
                }
            }
        }
    }
}
