pipeline {
    agent any
    tools {
    	maven 'mvn'
    	jdk 'java' 
    }
    stages {
        stage('Build') {
            steps {
                bat 'mvn clean'
            }
        }
        stage('Test') {
            steps {
            	bat 'mvn verify'
            }
        }
    }
    post('Publish Reports') {
    	always {
    		junit 'target/failsafe-reports/junitreports/*.xml'
		}
    }
}