pipeline {
    agent any
    stages {
        stage('Compile') {
            steps { 
                sh 'mvnnn compile'
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
            }
        }
    }
    post {
      success {
          emailext body: '${BUILD_NUMBER}', subject: 'Hurray!!! the build has completed with Status ${BUILD_STATUS}', to: 'devopsxprts@gmail.com'
      }
      failure {
          emailext body: '${BUILD_NUMBER}', subject: 'Alas!! the build has completed with Status ${BUILD_STATUS}', to: 'devopsxprts@gmail.com'
      }
}
}
