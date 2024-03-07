pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Build the project with Maven
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                // Run the tests and generate the Surefire reports
                sh 'mvn clean test surefire-report:report'
            }
            post {
                // Publish the JUnit test results
                junit '**/target/surefire-reports/TEST-*.xml'
            }
        }
    }

