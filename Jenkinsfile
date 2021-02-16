pipeline {
  
    agent any

    tools {
        maven 'maven-3.6.3'
        jdk 'jdk11'
    }

    options {
        buildDiscarder(logRotator(numToKeepStr: '20', artifactNumToKeepStr: '30'))
    }

    triggers{
        pollSCM('H/5 * * * *')
    }


    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

    }
}