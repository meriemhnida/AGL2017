pipeline {
    agent any
    tools {
        maven 'Maven 3.5.2'
        jdk 'jdk1.8.0_151'
    }
    stages {
        stage ('Initialize') {
            steps {
            }
        }

        stage ('Build') {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true install' 
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
    }
}