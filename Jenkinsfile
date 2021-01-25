pipeline {
    options {
        buildDiscarder(logRotator(numToKeepStr: '15'))
    }

    agent {
        node {
            label 'docker'
        }
    }

    
    stages {
       stage('NPM Dependency Install') {
            def response = httpRequest "http://httpbin.org/response-headers?param1=${param1}"
            println('Status: '+response.status)
            println('Response: '+response.content)
        }        
    }
}
