pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning repository...'
                git branch: 'master', url: 'https://github.com/nyanyilinn/test.git'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying to XAMPP...'
                bat 'xcopy "%WORKSPACE%\\*" "D:\\xampp\\htdocs\\testing\\" /E /H /C /I /Y'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed! Check the logs for details.'
        }
        success {
            echo 'Pipeline succeeded! Deployment complete.'
        }
    }
}
