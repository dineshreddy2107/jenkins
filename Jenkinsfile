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
            input {
            message "Should we continue?"
            ok "Yes, we should"
            submitter "alice"
            parameters {
                string(name: 'person', defaultValue: 'Mr jenkins', description: 'who should i say hello to?')
            }
            }
            steps {
                script {
                    echo "hello, ${PERSON}, nice to meet you."
                    echo 'Deploying..'
                }
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