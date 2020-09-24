@Library('shared-library-github')_
pipeline {
    agent any
    options {
        skipDefaultCheckout true
    }
    tools {
        maven 'Maven3' 
    }
    stages {
        stage('checkout SCM'){
            steps{
                script{
                    echo 'before ==============='
                    toCheckout([
                        branches:[[name:'*/master']],
                        userRemoteConfigs:[[url:'https://github.com/KosuriKomaladevi/HelloWorld.git']]
                    ])
                    echo 'after =================='
                }
            }
        }
      

    }
}
