@Library('shared-jenkins-lib@master')
log.info 'starting'

pipeline {
    options {
        buildDiscarder(logRotator(numToKeepStr: '15'))
    }
    agent any
    
    stages {
       stage('NPM Dependency Install') {
           steps {
                echo 'API Call'

                script { 
                    def response = httpRequest "http://localhost:3000/users/"
                    println('Status: '+response.status)
                    println('Response: '+response.]
                }
           }
        }        
    }
}
