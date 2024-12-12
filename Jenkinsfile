pipeline {
    agent {
        node {
            label 'Agent-1'
            
        }
    }

    environment {
        GREETING = "Hello Jenkins"
    }

    //build
    stages {
        stage('Build') {
            steps {
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
                sh """
                echo 'Here I wrote shell-script'
                env
                """
            }
        }

    }

    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'this runs when pipelines fails & it is used to send some alerts'
        }
        success { 
            echo 'I will say Hello when pipeline is success'
        }
        

        
    }
}