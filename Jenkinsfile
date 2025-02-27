pipeline {
    agent any

    environment {
        SONARQUBE_SERVER = 'SonarQube'  // The name you configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    def branch = env.BRANCH_NAME ?: 'master' // Default to 'main' if not detected
                    git branch: branch, url: 'https://github.com/VarunChavda78/Jenkins-test.git'
                }
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    bat 'mvn sonar:sonar'
                }
            }
        }

        stage('Build') {
            steps {
                echo "Building the project..."
            }
        }

        stage('Check for Changes') {
            steps {
                script {
                    def fileContent = readFile('Test1.txt')
                    echo "File Content: ${fileContent}"
                }
            }
        }
    }
}
