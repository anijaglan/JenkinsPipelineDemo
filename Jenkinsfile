pipeline {
    agent any

    stages {
        stage('Clean') {
            steps {
                echo 'Clean..'
		bat 'mvn clean'
            }
        }
	stage('Build') {
            steps {
                echo 'Building..'
		bat 'mvn clean package -DskipTests'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
		bat 'mvn test'
            }
        }
	stage('Analysis') {
            steps {
                echo 'Building..'
		bat 'mvn sonar:sonar -Psonar'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
	stage('Info') {
            steps {
                echo 'Running ${env.BUILD_NUMBER} on ${env.BUILD_URL}'
            }
        }
    }
}
