pipeline {
    agent any

    stages {
        stage('Install Angular') {
            when {
                anyOf{
                    branch 'develop';
                    branch 'preprod';
                    branch 'master';
                    branch 'sonar';
                    tag "Version_1*"
                }
            }
            steps {
                echo 'Building..'
            }
        }
        stage('Build Angular') {
             when {
                anyOf{
                    branch 'develop';
                    branch 'preprod';
                    branch 'master';
                    branch 'sonar';
                    tag "Version_1*"
                }
            }
            steps {
                echo 'Building..'
            }
        }
        
        stage('Build C#') {
             when {
                anyOf{
                    branch 'develop';
                    branch 'preprod';
                    branch 'master';
                    tag "Version_1*"
                }
            }
            steps {
                echo 'Building..'
            }
        }
        
        stage('Code Analysis') {
             when { branch 'sonar' }
            steps {
                powershell(returnStdout: true, script: '''
                    Write-Host("Getting Host IP Address") -ForegroundColor Cyan
                    cmd.exe /c ipconfig
                ''')
                
            }
        }
        
        stage('Angular UnitTest') {
             when {
                anyOf{
                    branch 'develop';
                    branch 'preprod';
                    branch 'master';
                    tag "Version_1*"
                }
            }
            steps {
                echo 'Building..'
            }
        }
        stage('C# UnitTest') {
             when {
                anyOf{
                    branch 'develop';
                    branch 'preprod';
                    branch 'master';
                    tag "Version_1*"
                }
            }
            steps {
                echo 'Testing..'
            }
        }
        stage('ShipToOctopus') {
            when {
                anyOf{
                    branch 'develop';
                    branch 'preprod';
                    branch 'master';
                    tag "Version_1*"
                }
            }
            steps {
                echo 'Deploying....'
            }
        }
        
        stage('HappyDance') {
            steps {
                echo 'Building..'
            }
        }
    }
}
