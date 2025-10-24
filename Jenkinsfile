pipeline {
    agent any
    tools {
        jdk 'JDK21'
    }
    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/anil91608/jenkins-node-jdk21.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mynodeapp-jdk21:latest .'
            }
        }
        stage('Run Container') {
            steps {
                sh 'docker stop myapp || true'
                sh 'docker rm myapp || true'
                sh 'docker run -d -p 3000:3000 --name myapp mynodeapp-jdk21:latest'
            }
        }
    }
}
