pipeline {
    agent {
        label 'AGENT-1'
    }
    options { 
        // Timeout counter starts BEFORE agent is allocated
        timeout(time: 30, unit: 'MINUTES') 
        disableConcurrentBuilds()
        ansiColor('xterm')
    }
    environment {
        def appVersion = ''
        def nexusUrl = 'nexus.puneeth.cloud:8081'
    }
    parameters {
        string(name: 'appVersion', defaultValue: '1.0.0', description: 'What is the application version?')
    }
    stages {
        stage('Print the Version') {
            steps {
                script {
                  sh "echo Application Version:${appVersion}"
                }                
            }
        }
        // stage('Init') {
        //     steps {
        //         sh """
        //             cd terraform
        //             terraform init
        //         """               
        //     }
        // }
        // stage('Plan') {
        //     steps {
        //         sh """
        //             cd terraform
        //             terraform plan -var="app_version=${params.appVersion}
        //         """               
        //     }
        // }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
            deleteDir()
        }
        success{
            echo 'I will when pipeline is success'
        }
        failure{
            echo 'I will when pipeline is failure'
        }
    }
}
    

