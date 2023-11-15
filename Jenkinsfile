pipeline {
    agent { label 'windows'}
    
    stages {
        stage ('Build Prod') {
            when {
                branch "main"
            }
            steps {
                powershell '.\\build.ps1'
                powershell 'Move-Item -Path buildProd.txt -Destination d:\\jenkins-agent'
            }
        }
        stage ('Build QA') {
            when {
                branch "QA"
            }
            steps {
                powershell '.\\build.ps1'
                powershell 'Move-Item -Path buildQA.txt -Destination d:\\jenkins-agent'
            }
        }
        stage ('Build feature') {
            when {
                branch "feature-*"
            }
            steps {
                powershell '.\\build.ps1'
                powershell 'Move-Item -Path buildFeature.txt -Destination d:\\jenkins-agent'
            }
        }



    }
}