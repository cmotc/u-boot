pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'make CROSS_COMPILE=arm-linux-gnueabihf-'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh 'make full'
            }
        }
    }
}
