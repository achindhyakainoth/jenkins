pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'Java'
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
                sh 'java -cp target/classes Test'
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
