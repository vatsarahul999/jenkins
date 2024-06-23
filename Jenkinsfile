pipeline {
    agent any

    tools {
        maven 'maven 3.6.3'
        jdk 'jdk17'   // Ensure this matches the name configured in Jenkins
    }

    environment {
        MY_JOB = 'This is my Jenkins job'
        JAVA_HOME = "${tool name: 'jdk17', type: 'jdk'}"
        PATH = "${env.JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Initialize') {
            steps {
                sh 'echo $MY_JOB'
                sh 'echo $PATH'
            }
        }
        
        stage('Build') {
            steps {
                sh 'echo $MY_JOB'
                sh 'echo JAVA_HOME=$JAVA_HOME'
                sh 'echo PATH=$PATH'
                sh 'mvn clean install'
            }
        }
    }

    post {
        success {
            echo 'Build and test completed successfully!'
        }
        failure {
            echo 'Build or test failed.'
        }
    }
}