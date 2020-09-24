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
                        userRemoteConfigs: [[url:'https://github.com/KosuriKomaladevi/HelloWorld.git']]
                    ])
                    echo 'after =================='
                }
            }
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
        stage('building stage'){
            steps{
                script{
                    echo '============entered into build stage========================'
                    toBuild
                }
            }
        }
        stage('package'){
            steps{
                script{
                     echo '============entered into package stage========================'
                    packaging()
                }
            }
        }
        stage('JFrog artifactory'){
            steps{
                script{
                    echo '======================entered into Jfrog artifactory====================='
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
