pipeline {
    agent {
        label 'job1'
    }
    tools {
        maven 'maven3'
        jdk 'jdk17'
    }

    stages {
        stage('clean up the workspace') {
            steps {
                cleanWs()
            }
        }
        stage('checkout') {
            steps {
                git branch: 'main', credentialsId: 'gitcred', url: 'https://github.com/yevine/ut-registration-app'
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('test') {
            steps {
                sh 'mvn test'
            }
        }

    }
}
