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
