@Library('shared-jenkins-lib@master')
org.foo.Js

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
