pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from Git repository
                git 'https://github.com/your_username/my-java-project.git'
            }
        }
        
        stage('Build') {
            steps {
                // Build the Maven project
                script {
                    try {
                        sh 'mvn clean package'
                    } catch (Exception e) {
                        currentBuild.result = 'FAILURE'
                        echo "Build failed: ${e.message}"
                        error "Build failed: ${e.message}"
                    }
                }
            }
        }
        
        // Define other stages as needed...
    }
    
    post {
        always {
            // Send notification or trigger other jobs upon completion (success or failure)
            echo 'Build completed. Sending notifications...'
        }
    }
}
