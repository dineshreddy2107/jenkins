pipeline {
    agent  {
      label 'AGENT-1'  
    }
    environment {
        COURSE = 'jenkins'
    }

    stages {
        stage('Build') {
            steps {
                script {
                    sh """
                     echo "hello build"
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