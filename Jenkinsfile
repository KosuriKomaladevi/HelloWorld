@Library('shared-library-github')_
pipeline {
    agent any
    options {
        skipDefaultCheckout true
    }
    tools {
        maven 'Maven3' 
    }
     stage('Maven Version') {
            steps {
                script{
                    echo '===================entered into maven version================'
                    sample 'Komaladevi Kosuri' 
                    bat 'mvn --version'
                }
            }
    }
}
