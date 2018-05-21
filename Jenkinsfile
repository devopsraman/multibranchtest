pipeline {
    agent any
    
    properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '200')), parameters([string(defaultValue: 'master', description: 'branchname', name: 'GIT_REFERENCE_VALUE', trim: false), booleanParam(defaultValue: false, description: 'sip file ', name: 'Test_BUILD_BUNDLE')])])
    
    stages {
        stage('Example') {
            steps {
                echo 'Hello World'
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
