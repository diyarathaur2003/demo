pipeline {
    agent any
    
    

    stages {
        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/diyarathaur2003/demo.git'
                echo 'Installing dependencies...'
                echo 'Building the React application.'
                
            }
        }
        stage('Unit Tests and Integration Tests') {
            steps {
                echo 'Running  all unit tests...'
                echo 'Running the Integration Tests...'
                
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analysis of the code by tools like '
            }
        }
      stage('Security Scan') {
            steps {
                echo 'Performing security scan of the overall project for any security risks...'
                
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
            
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Final stage of the deployement using various deployement platforms such as Netlify..'
            }
        }
    }
    
    post {
        success {
            
            script {
               
                def powershellCommand = """
                    \$SMTPServer = "smtp.gmail.com"
                    \$SMTPFrom = "diyarathaur312@gmail.com"
                    \$SMTPTo = "diyarathaur312@gmail.com"
                    \$SMTPSubject = "SUCCESSFULLY COMPLETED "
                    \$SMTPBody = "PIPELINE EXECUTED SUCCESSFULLY!!"
                    \$SMTPUsername = "diyarathaur312@gmail.com"
                    \$SMTPPassword = ""
    
                    Send-MailMessage -From \$SMTPFrom -to \$SMTPTo -Subject \$SMTPSubject -Body \$SMTPBody -SmtpServer \$SMTPServer -UseSsl -Port 587 -Credential (New-Object System.Management.Automation.PSCredential \$SMTPUsername, (ConvertTo-SecureString -AsPlainText \$SMTPPassword -Force))
                """
                powershell(powershellCommand)
            }
            
            echo 'SUCCESSFULLY COMPLETED!'
        }
        failure {
           
            script {
               
                def powershellCommand = """
                    \$SMTPServer = "smtp.gmail.com"
                    \$SMTPFrom = "diyarathaur312@gmail.com"
                    \$SMTPTo = "diyarathaur312@gmail.com"
                    \$SMTPSubject = "FAILED, CHECK"
                    \$SMTPBody = "FAILED TO EXECUTE!!"
                    \$SMTPUsername = "diyarathaur312@gmail.com"
                    \$SMTPPassword = ""
    
                    Send-MailMessage -From \$SMTPFrom -to \$SMTPTo -Subject \$SMTPSubject -Body \$SMTPBody -SmtpServer \$SMTPServer -UseSsl -Port 587 -Credential (New-Object System.Management.Automation.PSCredential \$SMTPUsername, (ConvertTo-SecureString -AsPlainText \$SMTPPassword -Force))
                """
                powershell(powershellCommand)
            }
            echo 'FAILED, CHECK.'
        }
    }
}
