pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    docker.withServer('tcp://192.168.1.110:2376') {
                        // tus pasos de construcción aquí
                         docker.image('maven:3.8.5-eclipse-temurin-17').inside {
                        sh 'mvn clean package -DskipTest -B -ntp'
                    }
                    }
                }
            }
        }
    }
}

