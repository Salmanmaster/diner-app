pipeline {
    agent any
    
    stages{
    stage('build'){
        steps {
            echo 'Building started..'
        }
    }
   stage('Test'){
        steps {
            sh 'netstat -nltup |grep 8080'
            echo 'Jenkins is running'
        }
    }
    stage('Deploy'){
        steps {
            sh 'cd /var/www/html-sample-app && sudo git pull'
        }
    }
    }
    }

