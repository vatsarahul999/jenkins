pipeline {
	agent any
	tools {
	 maven 'maven 3.6.3'
	 jdk 'jdk17'
	}
	environment {
		MY_JOB = 'This is my Jenkins job'
		JAVA_HOME =../JAVA_HOME_17
	}
	stages {
		stage('Initialize'){
			environment {
				MY_INIT_VAR='Initialize env var'
			}
			steps {
			sh 'echo $MY_JOB'
			sh 'echo $MY_INIT_VAR'
			}
		}
		stage ('Build') {
		steps {
			sh 'echo $MY_JOB'
			sh 'mvn clean install'
		}
		}
	
	}
	


}