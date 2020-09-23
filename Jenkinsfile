@Library('shared-library-github')_
pipeline {
    agent any
    stages {
        stage('Shared1') {
            steps {
                script{
                    sample 'Komaladevi Kosuri'
                }
            }
        }
        stage('package'){
            steps{
                script{
                    packaging
                }
            }
        }
    }
}
