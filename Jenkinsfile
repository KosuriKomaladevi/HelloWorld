@Library('shared-library-github')_
pipeline {
    agent any
    stages {
        stage('Stage1') {
            steps {
                script{
                    sample.call
                    echo 'shared library working'
                }
            }
        }
    }
}
