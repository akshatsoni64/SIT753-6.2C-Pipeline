pipeline {
    agent any

    stages {
        stage('Build') {
            environment{
                DIRECTORY_PATH = '/dev'
            }
            steps {
                echo "Fetcing the source code from ${env.DIRECTORY_PATH}"
                echo 'Compiling the code and generating artifacts using Maven...'
                sleep 5
                echo 'Done'
            }
        }
        stage('Testing') {
            steps {
                echo 'Executing Unit Tests using JUnit:'
                echo 'Test 1'
                sleep 2
                echo 'Done'
                echo 'Test 2'
                sleep 2
                echo 'Done'
                echo 'Test 3'
                sleep 2
                echo 'Done'
                echo 'Executing Integration Tests using Selenium:'
                echo 'Test 1'
                sleep 2
                echo 'Done'
                echo 'Test 2'
                sleep 2
                echo 'Done'
                echo 'Test 3'
                sleep 2
                echo 'Done'
            }
            post{
                success{
                    emailext attachLog: true, body: "Unit and Integration testing successfully completed!", subject: "Testing Status Email", to: 's223712753@deakin.edu.au'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Checking the source code quality using PMD'
                sleep 5
                echo 'Done'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Checking the source code quality using SonarQube'
                sleep 5
                echo 'Done'
            }
            post{
                success{
                    emailext attachLog: true, body: "Security scan was successful!", subject: "Security Scan Status Email", to: 's223712753@deakin.edu.au'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application to App Engine Instance'
            }
        }
        stage('Staging Testing') {
            steps {
                echo 'Executing Integration Tests using Selenium:'
                echo 'Test 1'
                sleep 2
                echo 'Done'
                echo 'Test 2'
                sleep 2
                echo 'Done'
                echo 'Test 3'
                sleep 2
                echo 'Done'
            }
            post{
                success{
                    emailext attachLog: true, body: "Unit and Integration testing successfully completed on Staging Environment!", subject: "Staging Test Status Email", to: 's223712753@deakin.edu.au'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying the application to Production App Engine Instance.'
            }
        }
    }
}
