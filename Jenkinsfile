pipeline {
    agent any 
    stages {
        stage('build') { 
            steps {
                echo 'Node Modules Installation...'
                bat 'npm install'
            }
        }
        stage('test') { 
            steps {
                echo 'Building App..'
                bat 'set "REACT_APP_TESTVAR=abcdef" && npm run build'
            }
        }
        stage('deploy') { 
            steps {
                echo 'Docker Config'
                bat "docker pull httpd"
                bat "docker build -t reactapp"
                bat "docker run --name dockerreact -p 5000:80 reactapp"
            }
        }
    }
}

