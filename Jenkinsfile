pipeline {
    agent {
        label "windows"
    }
    tools {
        maven 'Maven 3.5.2'
        jdk 'jdk1.8.0_151'
    }
    stages {
        stage ('Initialize') {
            steps {
                bat '''
                    echo "PATH = %PATH%"
                    echo "M2_HOME = %M2_HOME%"
                '''
            }
        }

        stage ('Build') {
            steps {
                    bat 'mvn install'
            }
             post {
                success {
                    junit 'HelloWorld/target/surefire-reports/*.xml'
                        }
                 }
               

           
            }
        }
    
}