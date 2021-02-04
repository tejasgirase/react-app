@Library('shared-jenkins-lib') _


pipeline {
    options {
        buildDiscarder(logRotator(numToKeepStr: '15'))
    }
    agent any

    stages {
        evenOrOdd(0)
        stage ('Run only if approval exists') {
            steps {
                sayHello 'tejas'
                echo "The build has been approved!!!"
            }
        }

       stage('NPM Dependency Install') {
           steps {
                echo 'API Call'
           }
        }        
    }
}
