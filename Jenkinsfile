@Library('shared-library-github')_
pipeline {
    agent any
    
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

