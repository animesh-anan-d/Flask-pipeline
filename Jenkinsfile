pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/animesh-anan-d/Flask-pipeline.git'
            }
        }

        stage('Build') {
            steps {
                sh 'python3 -m venv venv'
                sh '. venv/bin/activate && pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                sh '. venv/bin/activate && pytest'
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                echo "Deploying the Flask app to staging environment..."
            }
        }
    }

    post {
        success {
            mail to: 'animesh.anand2001@example.com',
                 subject: "SUCCESS: Jenkins build ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                 body: "Good news! The build succeeded."
        }
        failure {
            mail to: 'animesh.anand2001@example.com',
                 subject: "FAILURE: Jenkins build ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                 body: "Oops! The build failed."
        }
    }
}
