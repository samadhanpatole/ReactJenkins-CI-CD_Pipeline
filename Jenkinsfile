pipeline {
    agent any

    stages {

        stage("Install Dependencies") {
            steps {
                bat "npm install"
            }
        }

        stage("Test") {
            steps {
                bat "npm test -- --watchAll=false --passWithNoTests"
            }
        }

        stage("Build") {
            steps {
                bat "npm run build"
            }
        }

        stage("Deployment") {
            steps {
                bat "if exist C:\\inetpub\\wwwroot\\reactapp rmdir /s /q C:\\inetpub\\wwwroot\\reactapp"
                bat "mkdir C:\\inetpub\\wwwroot\\reactapp"
                bat "xcopy /E /Y /I build\\* C:\\inetpub\\wwwroot\\reactapp\\"
            }
        }
    }
}