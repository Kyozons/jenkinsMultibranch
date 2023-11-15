pipeline {
    agent { label 'windows'}
    
    stages {
        stage ('Build') {
            steps {
                powershell 'build.ps1'
                powershell 'Move-Item -Path buildProd.txt -Destination d:\jenkins-agent'
            }
        }

    }
}