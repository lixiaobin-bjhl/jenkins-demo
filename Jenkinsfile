pipeline {
    agent any
    environment {
        STUFF = "${MTI_HOME}/linux:${MTI_HOME}/bin:${QUARTUS_HOME}/bin:${DCP_LOC}/bin"
        CI = 'true'
    }
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:6-alpine'
                    args '-p 3000:3000'
                }
            }
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "lixiaobin test"'
                sh 'pwd'
                sh 'cat ${WORKSPACE}/jenkins/scripts/test.sh'
                sh '${WORKSPACE}/jenkins/scripts/test.sh'
            }
        }
    }
}