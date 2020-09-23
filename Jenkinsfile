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
        stage('JFrog artifactory'){
            steps{
                script{
                    echo 'entered into Jfrog artifactory'
                    def server = Artifactory.server('artifactory')
                      def rtMaven = Artifactory.newMavenBuild()
                      rtMaven.resolver server: server, releaseRepo: 'libs-release', snapshotRepo: 'libs-snapshot'
                      rtMaven.deployer server: server, releaseRepo: 'libs-release-local', snapshotRepo: 'libs-snapshot-local'
                      rtMaven.tool = 'Maven3'
                      def buildInfo = rtMaven.run pom: 'pom.xml', goals: 'install'
                      server.publishBuildInfo buildInfo
                }
            }
        }

    }
}
