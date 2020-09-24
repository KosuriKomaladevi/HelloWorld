@Library('shared-library-github')_
pipeline {
    agent any
   
    stages{
     stage('checkout Git SCM'){
            steps{
                script{
                toCheckout([
                        branch: "master",
                        url: "https://github.com/KosuriKomaladevi/HelloWorld.git"
                    ])
                }
                  
            }
        
        }
    }
}
