pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    // Establece el servidor remoto de Docker y la ruta donde está el Docker CLI
                    docker.withServer('tcp://192.168.1.110:2376', '/usr/bin/docker') {
                        // Aquí se utiliza una imagen de Maven para realizar la construcción
                        docker.image('maven:3.8.5-eclipse-temurin-17').inside {
                            // Ejecuta 'mvn clean package' dentro del contenedor Maven
                            sh 'mvn clean package -DskiptTest -B -ntp'
                        }
                    }
                }
            }
        }
    }
}


