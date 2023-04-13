pipeline {
    agent {
        any {
            image 'node:lts-bullseye-slim' 
            args '-p 8000:8000' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }

        stage('Deploy') { 
            steps {
                sh 'npm start &' 
                sleep 1
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh 'echo ByeBye'
            }
        }
    }
    
}
