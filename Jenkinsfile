pipeline {
    agent any
    
    

    stages {
        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/diyarathaur2003/demo.git'
                echo 'Installing dependencies...'
                // Example: npm install for installing dependencies
             
                echo 'Building the React application...'
                
            }
        }
        stage('Unit Tests') {
            steps {
                echo 'Running unit tests...'
                // Example run the npm tests for unit tests. 
                
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analysis of the code...'
                // Example: Running static code analysis tools like ESLint, SonarQube, etc
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan of the overall project for any security risks...'
                //Example: Running security scanning tools like SonarQube Security Analyzer, etc.
                
            }
        }
        stage('Deploy to Staging') {
            steps {
                 echo 'Deploying the application to a staging environment... for example using DOCKER'
                
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                 echo 'Running the integration tests on the staging environment...'
                //Example: Using Selenium, Cypress, or other frameworks for automated UI testing on the staging environment
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Final stage of the deployement using various deployement platforms'
                // Example Using Netlify or Render for deployement
                
            }
        }
    }
    
    post {
        success {
            emailext subject: "Pipeline '${currentBuild.fullDisplayName}' Successful",
                      body: 'Successfully Implemented. Congratulations!',
                      to: 'diyarathaur312@gmail.com',
                      attachLog: true
        }
        failure {
            emailext subject: "Pipeline '${currentBuild.fullDisplayName}' Failed",
                      body: 'Failed, Please investigate.',
                      to: 'diyarathaur312@gmail.com',
                      attachLog: true
        }
    }
}
