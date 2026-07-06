pipeline {
    agent any

stage('Verify Files') {
    steps {
        sh '''
        pwd
        ls -R
        '''
    }
}
    stages {
        stage('Deploy') {
            steps {
                sh '''
                sudo rm -rf /var/www/html/*
                sudo cp -r index.html style.css script.js images /var/www/html/
                sudo systemctl restart nginx
                '''
            }
        }
    }

    post {
        success {
            echo 'Deployment Successful!'
        }
        failure {
            echo 'Deployment Failed!'
        }
    }
}
