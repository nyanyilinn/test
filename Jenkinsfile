pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/nyanyilinn/test.git'
            }
        }

        stage('Test') {
            steps {
                bat 'C:\\xampp\\php\\php.exe '
                // Or use 'sh' for Linux/Mac:
                // sh '/opt/lampp/bin/php /opt/lampp/htdocs/your-project/tests/run-tests.php'
            }
        }

        stage('Deploy') {
            steps {
                bat 'xcopy D:\\xampp\\htdocs\\testing\\* D:\\xampp\\htdocs\\testing\\ /E /H /C /I'
                // Or use 'sh' for Linux/Mac:
                // sh 'cp -r /path/to/your/project/* /opt/lampp/htdocs/your-project/'
            }
        }
    }
}