pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clone the GitHub repository
                git branch: 'master', url: 'https://github.com/nyanyilinn/test.git'
            }
        }

        stage('Test') {
            steps {
                // Run PHP tests (if any)
                bat 'D:\\xampp\\php\\php.exe D:\\xampp\\htdocs\\testing\\tests\\run-tests.php'
                // Replace the path above with the actual path to your PHP test script
            }
        }

        stage('Deploy') {
            steps {
                // Copy files from the Jenkins workspace to the XAMPP htdocs directory
                bat 'xcopy "D:\\xampp\\htdocs\\testing\\*" "D:\\xampp\\htdocs\\testing\\" /E /H /C /I /Y'
                // The /Y flag suppresses prompting to confirm overwriting files
            }
        }
    }
}
