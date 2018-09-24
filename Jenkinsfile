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
                //fleg
                jdk "JDK8"
            }
            steps {
                sh test
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
