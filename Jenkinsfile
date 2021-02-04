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
                cmd('dir')
            }
        }

        stage('Check Unix') {
            steps {
                cmds('dir')
            }
        }        
    }
}

def cmds(command) {
    // при запуске Jenkins не в режиме UTF-8 нужно написать chcp 1251 вместо chcp 65001
    if (isUnix()) { sh "${command}" } else { bat "chcp 65001\n${command}"}
}
