
pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                echo 'clone'
            }
        }
        stage('build') {
            steps {
                echo 'build'
            }
        }
    }
        post{
            always{
                emailext body: 'summary', subject: 'pipeline status', to: 'catchmetejubhat@gmail.com'
            }
        }
    }
