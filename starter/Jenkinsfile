pipeline {
    agent any
    tools {
        maven 'maven'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                dir(starter){
                    sh 'mvn -B clean package'
                }
            }
        }
        stage('Test') {
            steps {
                dir(starter){

                }
            }
            post {
                always {
                    junit 'starter/target/surefire-reports/*.xml'
                }
            }
        }
        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
