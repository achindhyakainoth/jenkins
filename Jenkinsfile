pipeline {
    agent any

    tools {
        maven 'maven'      // Maven name configured in Jenkins Global Tool Configuration         // JDK configured in Jenkins
    }

    stages {

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Run Test') {
            steps {
                sh 'java Test'
            }
        }
    }

    post {
        success {
            echo 'Build Successful'
        }
        failure {
            echo 'Build Failed'
        }
    }
}
