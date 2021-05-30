

pipeline {
    agent any
    parameters{     
        choice(name: 'VERSION', choices: ['1.0.1', '1.0.2', '1.0.3'], description:'')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
    environment{                       
        NEW_VERSION = '1.1.2'
        SERVER_CREDENTIALS = credentials('my-github-credentials')  
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building process..'     
            }
        }
        stage('Test') {
            when {
                expression {
                    params.executeTests
                }
            }
            steps {
                echo 'Testing process..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying process....'
                echo "Deploying version ${params.VERSION}"
            }
        }
    }
}
