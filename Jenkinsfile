@Library('shared-jenkins-lib') _


pipeline {
    options {
        buildDiscarder(logRotator(numToKeepStr: '15'))
    }
    agent any

    stages {
        stage ('Run only if approval exists') {
            steps {
                sayHello 'tejas'
                echo "The build has been approved!!!"
            }
        }
    
       stage('NPM Dependency Install') {
           steps {
                echo 'API Call'

                script { 
                    // def response = httpRequest "http://localhost:3000/users/"
                    // println('Status: '+response.status)
                }
           }
        }        
    }
}
