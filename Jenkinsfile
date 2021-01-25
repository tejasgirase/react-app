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
                    def response = httpRequest "http://httpbin.org/response-headers?param1=${param1}"
                    println('Status: '+response.status)
                    println('Response: '+response.content)
                }
           }
        }        
    }
}
