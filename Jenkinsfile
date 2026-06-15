pipeline {
    agent any  // Use any available agent

    tools {
        maven 'Maven'  // Ensure this matches the name configured in Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/shreelesha/MyMavenAppF.git'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'  // Run unit tests
            }
        }

        stage('Build') {
            steps {
                sh 'mvn compile'  // Run Maven build
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'  // Run unit tests
            }
        }

        
        
       
        stage('Run Application') {
            steps {
                // Start the JAR application
                sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar'
            }
        }

        
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
