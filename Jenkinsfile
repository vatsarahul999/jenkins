pipeline {
	agent any
	tools {
	'maven'
	}
	environment {
		MY_JOB = 'This is my Jenkins job'
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