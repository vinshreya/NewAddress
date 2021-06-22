pipeline {
    agent any
    stages {
        stage('Compile') {
            steps { 
                sh 'mvn compile'
            }
        }
        stage('test') {
            steps { 
                sh 'mvn test'
            }
        }
        stage('package') {
            steps { 
                sh 'mvn package'
                emailext body: '${BUILD_NUMBER}', subject: 'the build has completed with Status ${BUILD_STATUS}', to: 'devopsxprts@gmail.com'
            }
        }
    }
}
