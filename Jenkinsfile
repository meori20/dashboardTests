pipeline {
    agent any

    stages {
        stage ('BUILD') {
            tools {
                jdk "JDK8"
            }
            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn clean compile'
                }
            }
        }
        
        stage ('Deliver Stage') {
            tools {
                jdk "JDK8"
            }
            steps {
                sh '''
                    curl -o output.file http://speedtest.ftp.otenet.gr/files/test10Mb.db
                '''
            }
        }

    }
}