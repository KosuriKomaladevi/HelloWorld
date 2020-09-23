@Library('shared-library-github')_
pipeline {
    agent any
    tools {
        maven 'Maven3' 
    }
    stages {
        stage('Shared1') {
            steps {
                script{
                    sample 'Komaladevi Kosuri'
                    
                    bat 'mvn --version'
                }
            }
        }
        stage('package'){
            steps{
                script{
                    packaging()
                }
            }
        }
    }
}
