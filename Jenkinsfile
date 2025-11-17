pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK21'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/BouthaynaHammami/Bouthayna_Hammami_DevOps.git'
            }
        }

        stage('Build') {
            steps {
		dir('student-management') {
			sh 'mvn clean package'
		}
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'student-management/target/*.jar', fingerprint: true
            }
        }
    }
}
