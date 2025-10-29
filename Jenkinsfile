pipeline {
    agent any
     tools {
        maven 'Maven'
    }
    stages {
        stage('checkout') {
            steps {
                git url: 'https://github.com/Ramaraju413/jenkins-java-project.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('code quality') {
            steps {
                echo " my code is done with code quality testing"
            }
        }
        stage('artifact') {
            steps {
                sh 'mvn package'
            }
        }
        stage('s3') {
            steps {
               s3Upload consoleLogLevel: 'INFO', dontSetBuildResultOnFailure: false, dontWaitForConcurrentBuildCompletion: false, entries: [[bucket: 'venom12-nexus', excludedFile: '', flatten: false, gzipFiles: false, keepForever: false, managedArtifacts: false, noUploadOnFailure: false, selectedRegion: 'us-east-1', showDirectlyInBrowser: false, sourceFile: 'target/NETFLIX-1.2.2.war', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: false]], pluginFailureResultConstraint: 'FAILURE', profileName: 'Rama', userMetadata: []
            }
        }
        stage('deploye'){
            steps {
                echo "my code is deployeed by Santhu"
            }
        }
    }
}
