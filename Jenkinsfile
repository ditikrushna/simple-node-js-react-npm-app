pipeline {
    agent any 
    stages {
        stage("Installing NPM Packages") { 
            steps {
                bat "npm install"
            }
        }
        
        stage("Building React Application"){
            steps{
            echo "generate files and build folder"
            bat "npm run build"
            }
        }

        
        stage("deploy to apache ") { 
            steps {
                echo 'deploying react app to apache web server'
                bat "xcopy /s build C:\\Apache24\\htdocs"
            }
        }
    }
}

