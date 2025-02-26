pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/VarunChavda78/Jenkins-test.git'
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
