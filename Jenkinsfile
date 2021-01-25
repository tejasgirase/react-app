pipeline {
    options {
        buildDiscarder(logRotator(numToKeepStr: '15'))
    }
    agent none
    
    stages {
       stage('NPM Dependency Install') {
            agent {
                docker { image 'node:lts-alpine3.9' }
            }

            steps {
                script {
                    FAILED_STAGE=env.STAGE_NAME
                    sh '''
                        npm install
                        npm run build
                        npm t -- --coverage -u --watchAll=false
                    '''
                    stash name: "build", includes: "build/**/*"
                    stash name: "coverage", includes: "coverage/**"
                }
            }
        }

        stage('Dependency Vulnerability Analysis') {
            agent {
                docker {
                    image 'owasp/dependency-check:5.3.0'
                    args '-v /root/dependency-check-data:/usr/share/dependency-check/data --entrypoint='
                    }
            }
            steps {
                script {
                    FAILED_STAGE=env.STAGE_NAME
                    echo "Application Dependency Vulnerability Analysis"
                    sh "/usr/share/dependency-check/bin/dependency-check.sh -f ALL -s ."
                    stash name: "dependency-reports", includes: "dependency-check-report.*"
                    archiveArtifacts artifacts: 'dependency-check-report.*', fingerprint: true
                }
            }
        }

        
    }
}
