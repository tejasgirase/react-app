@Library('shared-jenkins-lib') _


// evenOrOdd(0)

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
                sh '''
                    npm install
                    npm run build
                    '''           
            }
        }        
    }
}
