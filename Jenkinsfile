pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    def branch = env.BRANCH_NAME ?: 'master' // Default to 'master' if not detected
                    echo "Triggered by branch: ${branch}" // Display branch name
                    git branch: branch, url: 'https://github.com/VarunChavda78/Jenkins-test.git'

                    // Show the latest commit details
                    def commitInfo = sh(script: 'git log -1 --pretty=format:"%an - %s"', returnStdout: true).trim()
                    echo "Last commit: ${commitInfo}"

                    // Show changed files
                    def changedFiles = sh(script: 'git diff --name-only HEAD~1 HEAD', returnStdout: true).trim()
                    echo "Changed files:\n${changedFiles}"

                    // Show the actual changes (added and modified lines)
                    def changes = sh(script: 'git diff --unified=0 HEAD~1 HEAD', returnStdout: true).trim()
                    echo "Code Changes:\n${changes}"
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
