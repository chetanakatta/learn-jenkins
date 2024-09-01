pipeline {
    agent {
        label 'AGENT-1' // our agent name
    }
    options {
        //after particular time job will be failed (timeout counter starts before agent is allocated)
        timeout (time: 30, unit: 'MINUTES')
    }
    stages {
        stage ('Build') {
            steps {
                sh 'echo this is build'
            }    
        }
        stage ('Test') {
            steps {
                sh 'echo this is test'
                sh 'sleep 10'
            }
        }
        stage ('deploy') {
            steps {
                sh 'echo this is deploy'
            }
        }
    }
}