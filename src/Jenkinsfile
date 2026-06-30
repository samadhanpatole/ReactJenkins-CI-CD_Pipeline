pipeline {
    agent any
 
    tools {
        nodejs "NodeJs"
    }
 
    stages {
 
        stage("Install Dependencies") {
            steps {
                bat "npm install"
            }
        }
 
        stage("Test") {
            steps {
                echo "Testing the application"
            }
        }
 
        stage("Build") {
            steps {
                bat "npm run build"
            }
        }
 
        stage("Deployment") {
            steps {
                bat "del /q /s C:\\inetpub\\wwwroot\\reactapp\\*"
                bat "xcopy /E /Y /I build\\* C:\\inetpub\\wwwroot\\reactapp\\"
            }
        }
    }
}