pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
        ansiColor('xterm')
    }
    parameters {
        string(name: 'APP_VERSION', defaultValue: '1.0.0', description: 'What is the app version?')
    }
    environment{
         APP_VERSION = '' // Variable Declaration
         NEXUS_URL = 'nexus.surya-devops.site:8081'
    }
    stages {
        stage('print the version'){
            steps{
                script{
                    echo "application version: ${params.APP_VERSION}"
                }
            }
        }

    }
    post {
        always {
            echo 'I will always say hello'
            deleteDir()
        }
        success {
            echo 'Shows Only upon success'
        }
        failure {
            echo 'shows upon failure'
        }
    }
}