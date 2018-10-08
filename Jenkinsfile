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
        
        stage ('Testing Stage') {
            tools {
                jdk "JDK8" //
            }
            steps {
                sh '''
                    curl -o output.file http://speedtest.ftp.otenet.gr/files/test100Mb.db
                '''
            }
        }
        
        stage ('Run Automation Tests') {
            tools {
                jdk "JDK8"
            }
            steps {
                sh '''
                    curl -o output.file http://speedtest.ftp.otenet.gr/files/test10Mb.db
                '''
            }
        }
        stage ('Check Build architecture') {
            tools {
                jdk "JDK8"
            }
            steps {
                sh '''
                    curl -o output.file http://speedtest.ftp.otenet.gr/files/test100Mb.db
                '''
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