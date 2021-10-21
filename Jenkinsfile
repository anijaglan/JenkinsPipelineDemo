pipeline {
    agent any

    stages {
        stage('Clean') {
            steps {
                echo 'Clean..'
				sh 'mvn clean'
            }
        }
		stage('Build') {
            steps {
                echo 'Building..'
				sh 'mvn clean package -DskipTests'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
				sh 'mvn test'
            }
        }
		stage('Analysis') {
            steps {
                echo 'Building..'
				sh 'mvn sonar:sonar -Psonar'
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
