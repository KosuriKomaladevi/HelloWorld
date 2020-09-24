@Library('shared-library-github')_
pipeline {
    agent any
    options {
        skipDefaultCheckout true
    }
    tools {
        maven 'Maven3' 
    }
    stages{
     stage('checkout SCM'){
            steps{
                toCheckout{
                        branch: "master"
                        url: "https://github.com/KosuriKomaladevi/HelloWorld.git"
                    }
                  
            }
        
        }
    }
}
