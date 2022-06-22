pipeline {



    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') {
            steps {
                echo $PATH
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}
