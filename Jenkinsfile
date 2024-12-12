pipeline {
    agent {
        node {
            label 'Agent-1'
            
        }
    }

    environment {
        GREETING = "Hello Jenkins"
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
        stage('check_params'){
            steps{
                sh """
                echo "Hello ${params.PERSON}"
                echo "Biography ${params.BIOGRAPHY}"
                echo "Toggle ${params.TOGGLE}"
                echo "Choice  ${params.CHOICE}"
                echo "password ${params.PASSWORD}"
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