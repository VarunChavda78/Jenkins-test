pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    def branch = env.BRANCH_NAME ?: 'master' // Default to 'master' if not detected
                    git branch: branch, url: 'https://github.com/VarunChavda78/Jenkins-test.git'
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
