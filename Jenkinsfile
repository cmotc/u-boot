pipeline {
    agent any
    stages {
        stage('Clean') {
            steps {
                echo 'Cleaning Up'
                sh 'make mrproper'
            }
        }
        stage('Build') {
            steps {
                echo 'Building'
                sh 'export ARCH=arm64 && export CROSS_COMPILE=aarch64-linux-gnu- && make pine64_plus_defconfig && make'
                sh 'export ARCH=armhf && export CROSS_COMPILE=armhf-linux-gnu- && wget -qO .config https://raw.githubusercontent.com/cmotc/android_product_antm_revo/master/antm_revo_a33_tablet_1024x600_defconfig && make antm_revo_a33_tablet_1024x600_defconfig && make'
                //sh 'export ARCH=arm64 && export CROSS_COMPILE=aarch64-linux-gnu- && make alldaymall_a64_tablet_1024x600_defconfig && make'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Cleaning Up'
                //sh 'make mrproper'
            }
        }
    }
}
