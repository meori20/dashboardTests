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
                    curl -o output.file http://speedtest.ftp.otenet.gr/files/test100Mb.db
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
