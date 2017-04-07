pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Cleaning Up'
                sh 'make mrproper'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Building'
                sh 'export ARCH=arm64 && export CROSS_COMPILE=aarch64-linux-gnu-&& make pine64_plus_defconfig && make'
                sh 'export ARCH=armhf && export CROSS_COMPILE=armhf-linux-gnu-&& make antm_revo_a33_tablet_1024x600_defconfig && make'
                //sh 'export ARCH=arm64 && export CROSS_COMPILE=aarch64-linux-gnu-&& make alldaymall_a64_tablet_1024x600_defconfig && make'
            }
        }
    }
}
