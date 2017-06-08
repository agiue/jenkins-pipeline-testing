pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                retry(3) {
                    sh './flakey-deploy.sh'
                }

                timeout(time: 10, unit: 'SECONDS') {
                    sh './health-check.sh'
                }
            }
        }
    }
}
