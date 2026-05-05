pipeline {
    agent  {
      label 'AGENT-1'  
    }
    environment {
        COURSE = 'jenkins'
    }
    options {
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
    stages {
        stage('Build') {
            steps {
                script {
                    sh """
                     echo "hello build"
                     echo "hello build11"
                     
                     env
                     """
                }
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post {
        always {
            echo 'I will always say Hello again!'
            deleteDir()
        }
        success {
            echo 'Hello Success'
        }
    }
}