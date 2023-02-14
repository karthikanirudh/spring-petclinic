pipeline {
    agent  { label 'OPENJDK-19' }
    stages {
        stage('vcs') {
            steps {
                git branch: 'test', url: 'https://github.com/karthikanirudh/spring-petclinic.git'
            }

        }
        stage('build') {
            steps {
                sh 'mvn package'
            }
        }
        stage('archive results') {
            steps {
                junit '**/surefire-reports/*.xml'
            }
        }
    }

}