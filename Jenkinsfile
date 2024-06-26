pipeline {
    agent any

    tools {
        maven 'maven 3.6.3'
        jdk 'jdk17'   // Ensure this matches the name configured in Jenkins
    }

    environment {
        MY_JOB = 'This is my Jenkins job'
        JAVA_HOME = tool name: 'jdk17', type: 'jdk'
        PATH = "${env.JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Initialize') {
            environment {
                MY_INIT_VAR = 'Initialize env var'
            }
            steps {
                sh 'echo $MY_JOB'
                sh 'echo $MY_INIT_VAR'
            }
        }
        
        stage('Build') {
            steps {
                script {
                    env.JAVA_HOME = tool name: 'jdk17', type: 'jdk'
                    env.PATH = "${env.JAVA_HOME}/bin:${env.PATH}"
                }
                sh '''
                    echo $MY_JOB
                    echo JAVA_HOME=$JAVA_HOME
                    echo PATH=$PATH
                    java -version
                    javac -version
                    mvn clean install
                '''
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
