pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building code using Maven..."
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit tests using JUnit..."
                echo "Running integration tests using Selenium..."
            }
        }

        stage('Code Analysis') {
            steps {
                echo "Analyzing code using SonarQube..."
            }
        }

        stage('Security Scan') {
            steps {
                echo "Performing security scan using OWASP ZAP..."
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Deploying to staging server AWS EC2..."
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests using Selenium..."
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying to production server AWS EC2..."
            }
        }
    }

     post {
        success {
            // Send success notification email with logs as attachment
            emailext (subject: 'Build Status',
                body: 'Build was successful.',
                to: 'colmealyss09@gmail.com',
                attachLog: true )
        }
        failure {
            // Send failure notification email with logs as attachment
            emailext (subject: 'Build Status',
                body: 'Build was unsuccessful.',
                to: 'colmealyss09@gmail.com',
                attachLog: true )
        }
    }
}
