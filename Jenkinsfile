def gv

pipeline {
    agent any
    parameters{
        choice(name: 'VERSION', choices: ['1.0.1', '1.0.2', '1.0.3'], description:'')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
    stages {
        stage('init'){
            steps{
                script{
                   gv = load('script.groovy')
                }
            }
        }
        stage('Build') {
            steps {
                script{
                    gv.buildApp()
                }
            }
        }
        stage('Test') {
            steps {
                script{
                    gv.testApp()
                }
            }
        }
        stage('Deploy') {
            steps {
               script{
                    gv.deployApp()
                }
            }
        }
    }
}
