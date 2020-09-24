@Library('shared-library-github')_
pipeline {
    agent any
     options {
        skipDefaultCheckout true
    }
    stages{
         stage('build stage'){
            steps{
                script{
                    toBuild()
                }
            }
        }
        stage('package stage'){
            steps{
                script{              
                    packaging()
                }
            }
        }
     stage('checkout Git SCM'){
            steps{
                script{
                toCheckout([
                        branch: "master",
                        url: "https://github.com/KosuriKomaladevi/HelloWorld.git"
                    ])
                }
                  
            }
       stage('Deploying to Artifactory'){
             steps{
                 script{
                    artifactory([
                        server : 'artifactory',
                        tool :"Maven3" 
                    ])
                 }
             }
         }
        
        }
    }
}
