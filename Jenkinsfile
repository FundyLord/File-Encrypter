pipeline {
    agent {
       label 'agent'
    }
    stages {

        stage('Build') {
            steps {
                sh '''
                echo "Building Java project..."
                cd "Password Protection"
                mkdir -p build
                javac -d build src/*.java
                echo "Build successful"
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''
                echo "Running test stage..."
                '''
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                echo "Packaging artifact..."
                cd "Password Protection"
                jar cf FileEncrypter.jar -C build .
                echo "Deployment stage complete"
                '''
            }
        }
    }
    post {
        success {
            echo "Pipeline executed successfully!"
        }
        failure {
            echo "Pipeline failed!"
        }
    }
}
