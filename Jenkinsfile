pipeline {
    agent {
        label 'AGENT-1' // our agent name
    }
    options {
        //after particular time job will be failed (timeout counter starts before agent is allocated)
        timeout (time: 30, unit: 'MINUTES')
        disableConcurrentBuilds () //disables multiple executions
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    environment {
        DEPLOY_TO = 'Production'
        GREETINGS = 'Morning'
    }
    stages {
        stage ('Build') {
            steps {
                sh 'echo this is build'
                sh 'env'
            }    
        }
        stage ('Test') {
            steps {
                sh 'echo this is test'
                //sh 'sleep 10'
            }
        }
        stage ('deploy') {
            steps {
                sh 'echo this is deploy'
            }
        }
        stage ('print params') {
            steps {
                echo "hello ${params.PERSON}"
                echo "biography: ${params.BIOGRAPHY}"
                echo "Tggle: ${params.TOGGLE}"
                echo "Password: ${params.PASSWORD}"
                echo "trigging test"
            }
        }
    }
}